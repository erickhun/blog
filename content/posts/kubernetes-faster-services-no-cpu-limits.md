+++
categories = ["kubernetes", "infrastructure"]
date = "2020-08-31T23:56:00+08:00"
description = ""
draft = false
image = "/img/about-bg.jpg"
title = "Kubernetes: Make your services faster by removing CPU limits"
+++

At Buffer, we've been using [Kubernetes since 2016](https://kubernetes.io/case-studies/buffer/). Our k8s (Kubernetes). We've been managing our cluster with [kops](https://kops.sigs.k8s.io), it has about 60 nodes (on AWS), and runs about 1500 containers. Our transition to a micro-service architecture has been full of trial and errors. Even after few years running k8s, we are still learning its secrets. This post will talk about how something we thought was right, but ended up to be bad: **CPU limits**.

## CPU limits and Throttling
[Google recommends](https://cloud.google.com/blog/products/gcp/kubernetes-best-practices-resource-requests-and-limits) to set CPU limits. The danger of not setting a CPU limit is that containers running in the node will exhaust all CPU available. This can trigger a cascade of unwanted events. It is in theory a great thing to set CPU limit in order to protect your nodes.

CPU limits is the maximum CPU time a container can use at a given period (100ms by default). The CPU usage for a container will never go above that limit you specified. Kubernetes use a mechanism called [CFS Quota](https://en.wikipedia.org/wiki/Completely_Fair_Scheduler) to **throttle** the container to prevent the CPU usage to go above the limit. That means CPU will be artificially restricted, making the performance of your containers lower (and slower when it come to latency).


## What can happen if we don't set CPU limits?
We unfortunately experienced the issue. The `kubelet` , a process running on every nodes, and in charge of managing the containners (pods)  in the nodes became unresponsive. The node will turn into a `NotReady` state, and containers (pods) that were present will be reschedule somehwere else, and create the issue in the new nodes. Definitely not ideal isn't it? 

## Discovering the throttling and latency issue
We were suspecting. A key metric to check would be the `throttling` , the number of time your container has been throttled. Interestingly, we've discovered a lot of containers having throttling no matter if the CPU usage was near the limits or not. 
Here the example of one of our main API:

![Kubernetes pods CPU usage and limits](/img/kubernetes-cpu-limits/cpu-usage-limits.png)

You can see in the animation that the CPU limits is set at `800m` (0.8 core, 80% of a core), and the peak usage is at most `200m` (20% of a core). After seeing, we might think we have plenty of CPU to let the service running before it throtlle right? . Now check this one out: 

![Kubernetes pods Low CPU usage, High limit, lot of throttling](/img/kubernetes-cpu-limits/cpu-throttling-low-usage.gif)

You can noticed the CPU throttling occurs, even though the CPU usage is below the CPU Limts. The maximum CPU usage isn't even near the CPU limits. 

We've then found few resources ( [github issue](https://github.com/kubernetes/kubernetes/issues/67577), [zanado talk](https://www.youtube.com/watch?v=LpFApeaGv7A&feature=youtu.be&t=1204),  [omio post](https://medium.com/omio-engineering/cpu-limits-and-aggressive-throttling-in-kubernetes-c5b20bd8a718)) talking about how throttling lead to poorer performances and latency for your services. 

**Why do we see CPU throttling while the container doesn't even use?**
I won't get into details, the tldr is basically  a bug in the Linux kernel throttling unecessarly containers with CPU limit. If you're curious about the nature of it, I invite you to check Dave Chiluk's [great talk]((https://www.youtube.com/watch?v=UE7QX98-kO0)), a [written version](https://engineering.indeedblog.com/blog/2019/12/unthrottled-fixing-cpu-limits-in-the-cloud/) also exists.
 

## Removing CPU limit
After many long discussions, we've decided to remove the CPU limits for all services that were directly or indirectly on the critical path of our users.

This wasn't an easy decisions since we value the stability of our cluster. We've experimented in the past some instability in our cluster with services using too much resources and disrupting all other services present in the same node.  That time was a bit different, we understood more how our services needs and had a good strategy to roll this out.

![Buffer-remove-cpu-limits-announcement](/img/kubernetes-cpu-limits/unleash-k8s.jpg)

## How to keep your nodes safe when removing limits ?

**Isolating "No CPU Limits" services**
Because in the past we've seen some node going down because some services were using too much 
I've also analyzed past month usage of all those services to make sure the CPU requests are properly set. Even if  the "slack" combined of all services in a given node should compensate the burst 

**Assigning the correct CPU and memory request**
The main worry we had was service using to much resources and lead to nodes becoming unresponsive. 
Because we now had solid observability of all services running in our cluster (with Datadog), I've analyzed few months of usage of each services we wanted to "unbound". I've simply assigned the maximum CPU usage as the CPU request. This will make sure to have allocated space in a node. If k8s won't try to schedule any other service in that node.

![Chose CPU request based on max](/img/kubernetes-cpu-limits/choose-cpu-request-based-on-max.png)

You can see in the graph that the peak CPU usage was `242m` CPU core (0.242 CPU core). Simply take this number and make it a bit higher to become the CPU request. You can notice that since the service is user facing, the peak CPU usage match to peak traffic time. 

Do the same with your memory usage and requests, and you will be all set!

The downside is that we lose in containers density, and have could end up with lot of "slack" during low traffic time . But this is an other story I'll deal with in a next post.

## Results
I'm happy to publish really great results after few weeks of experimentation, we've already seen really great latency improvements accross all the services we've modified:  

![faster-kubernetes-containers](/img/kubernetes-cpu-limits/speedup-no-cpu-limits.png)


The best result happened on our main landing page ([buffer.com](https://buffer.com)) where we speed the service up to **22x** faster! 🚀

![buffer.com speedup without cpu limits](/img/kubernetes-cpu-limits/no-cpu-limit-speedup-buffer-com.jpg)


<!-- ## Is the kernel bug fixed? 
Yes, it should be. We're still seing 


## What are the alternative solutions?
- Upgrade to the that include the patch
- Remove CPU limits
- Use a whole CPU core for each of your container (might not be great if you're looking into getting a high density of container running on a physical server )




EKS : Amazon  fixed the issue on [Dec 2019]( https://github.com/aws/containers-roadmap/issues/175#issuecomment-566785192),  you will need to use an AMI of at least `v20191213` version. 
GKE (Goggle Cloud) : I'm not too sure what's the state of it, but I believe it might have been fixed
kops : If you're using kops <. Recommnend to use 1.16

At Buffer, we're still under, then we could probably reinclude CPU limits. 

Who are affected ? 
https://github.com/kubernetes/kops/issues/8954




o "throttling" they are referring to cfs bandwidth control, nr_throttled in cpu.stat for the cgroup increasing. That is only enabled when cpu limits are enabled.

 the bug fix patches are still in the process of being incorporated into the myriad Linux distributions that someone might be using Kubernetes on.

 This was never an issue for people not using Linux distributions

Buffer: 
Now we use 
https://github.com/kubernetes/kops/blob/c5870ddf17bcc970ea7ba0793173063593ec02bb/channels/stable#L41 


## Takeaways
As for today, the bug has been fixed in the kernel. However 

- Upgrade your distribution if you can. 
- Understand the needs of your services
- Monitor your throttling
- 



-->

