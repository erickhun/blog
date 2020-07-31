+++
categories = ["remote", "sharing", "tech"]
date = "2020-07-30T23:44:22+08:00"
description = ""
draft = false
image = "/img/about-bg.jpg"
title = "Sharing Knowledge in a Remote team, across Timezones"
+++


> "True innovation comes an intersection of a cross-pollination of roles and ideas" - [Sunil](https://twitter.com/sunils34/), ex-CTO@Buffer


I've been working remotely at [Buffer](https://buffer.com) for 6 years now. As a software engineer, one of the critical skill I believe we ~~should~~ **must** have is being able to learn continuously. However, working in a fully distributed team, [splitted accross 10+ timezones](https://timezone.io/team/buffer), where we only meet each other [once a year](https://joel.is/the-power-of-company-retreats/), affects how you learn from your team, compared to if you were in a physical office.


With the current COVID-19 crisis, and where company suddenly switched to a work from home setup, understanding how the dynamic on knowledge flow in your engineering team is important. You don't want the knowledge shared being stopped.  I'll lay down some of our successful experiments, their pros and cons. 

## ❌🧠 The real miss opportunity in a remote team, knowledge sharing
In a remote team, we don’t have regular random opportunities to come together like we would in a physical office. Conversations will be focused within your current team conversation channel. You won't be able talk over the watercooler/coffee machine about your current issues with someone else than your core team.  You'll miss opportunities to talk with other teams about their challenges, bring up your expertise, and learn from someone else expertise from an other team. We stop learning as much as we could because we're not seing each other anymore. 

As a remote company, how do you overcome this challenge? How do you optimize knowledge sharing accross teams, no matter which timezone?
This is where the concept of regular snackchats at Buffer was born 3 years ago by [Sunil](https://twitter.com/sunils34/).


## 🍴💬 Snackchats

Snackchats are small talks that everyone can propose in the company. It can be any topics, from code, architecture, management, tips for a tool to side projects.  Anything really. We usually ask on slack, and if you  there is enough interest, you commit to it and prepare it. 
Here an example of [Tigran](https://tik.dev) asking interest on using Datadog Logs with APM together: 

![Snackchat Tigran asks interest](/img/snackchat-tigran-asks.png)

Here a great example of snackchat by [Hamish](https://hami.sh) on an "Intro to GitHub Actions":

{{< youtube M9sdqTc5_qg >}}

Also here some other great ones: 
- [Federico](https://twitter.com/federicoweber) on [git workflow](https://overflow.buffer.com/2018/06/08/snackchat-may-31-product-oriented-git-workflow/) 
- [Joe](https://joebirch.co) on "[Get started with Go](https://www.youtube.com/watch?v=j7OCVQD97WE)"

#### Tips for doing a snackchat
- Keep them short: 10 to 20 minutes, keep interest of your audience
- Record them, people will be able to see them later if they can't attend
- Your busy teamates will be able to see them at x2 speed
- Have a directory (notion/wiki) for future reference
- Like video call, putting a face, it's great to have a human touch to something "technical" to see someones smilling, worrying. 

#### The downsides of a Snackchat
The downside of snackchat is that takes quite a bit of energy to prepare. There can also be intimidating to ask if a topic you might want to present won't get enough interest from your workmates.
In a remote setting, people will try to make the best use of their time, and we might most of the time be busy on prioritties. The time you will set might not be the best fit for everyone. I wasn't able to participate to most of the snackchats because I live in a total different timezone than most of the people in the company. The tip here is to **make sure to record your snackchat** and repost it for people who couldn't attend them.

## ⚡️ Impromptu Knowledge Sharing Videos
An other format I personally enjoy doing is the "spontaneous" knowlege sharing . I'm in the Infrastructure, where product engineers might not necessarly have the need to understand what happens "behind the scene", but where the knowledge could be useful or pick their curiosity.

I especially enjoy that format for few reasons: 
- Snackchats requires preparations, and I know I will not be great at "live" presentations
- I'm more in the introvert side.  It require quite a bit of energy to ask interests, worrying if people. Sharing when I feel like it is a way that fits me and I'm satisfied with.
- My envy to create educative content isn't always consistent. There is some days where I will be more encline to share it and some where I'll not feel like it.

#### Tips on making "Impromptu Knowledge Sharing" videos
- I like using [Loom](https://www.loom.com). They make recording your screen and voice really easy. It also allows you to pause the recording, and aslso has an impressive online editor to trim your blanks.
- Try to keep the video dynamic, go to the point, and avoid the fluff, but keep the jokes
- Keep it short, ideally under 10 minutes
- When I know a video will be valuable on the long term, I try to do some Google slide to structure the video

Here an example where I wanted to show (not the first time) the benefits of using one of our internal librarie to make debuguing faster and easier: 
<div style="position: relative; padding-bottom: 62.5%; height: 0;"><iframe src="https://www.loom.com/embed/4a8605bdc5674ad3a551a37bfac09f3a" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>


## Use GIF to answer to questions
1 picture is worth a thousand words, but 1 GIF worth a video call. It can save you a lot of time, save you some context switching, and save your productivity. When someone has a question, a simple GIF of the solution will be more than enough than trying to jump on a call and explain. Calling someone, will require both of you some energy. The other party might also not be ready for that call. 

I enjoy using [cloudapp](https://www.getcloudapp.com/). For example here what I'll share when I wanted to share the results after migrating a service from PHP to Golang:

![PHP vs Golang CPU usage](/img/go-vs-php-cpu.gif)

## ❤️ Share without limits
Sharing links via Slack or email are great, but those content get easily lost. You shouldn't make assumptions your teamates saw the video you've shared once. I recommend to maintain a directory (in Notion/Paper/Wiki etc...). When you see a question that was answered in one of your video, share it again. Keep sharing. 

Over to you, what's your secrets on keeping your team in a remote setup? 
