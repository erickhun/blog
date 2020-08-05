+++
categories = ["remote", "sharing", "tech", "education"]
date = "2020-07-30T23:44:22+08:00"
description = ""
draft = false
image = "/img/about-bg.jpg"
title = "Sharing knowledge in a remote team, across timezones"
+++



![Share knowledge](/img/share-knowledge.jpg)


> "True innovation comes an intersection of a cross-pollination of roles and ideas" - [Sunil](https://twitter.com/sunils34/), former-CTO@Buffer


I've been working remotely at [Buffer](https://buffer.com) for 6 years now. As a software engineer, one of the critical skill I believe we ~~should~~ **must** have is being able to learn continuously. However, working in a fully distributed team, [split accross 10+ timezones](https://timezone.io/team/buffer). I live in Asia (UTC +8) while most of my teammates live in the US or Europe. That's up to 15 hours difference. We only meet each other [once a year](https://joel.is/the-power-of-company-retreats/). This remote setup affects how we learn from my team, compared to if I were in a physical office. 

With the current COVID-19 crisis, when company suddenly switched to a work from home setup, understanding how the dynamic of knowledge sharing in your team is important. You don't want the knowledge shared being stopped. I'll lay down some of our successful experiments, their pros and cons, what I think works for me and our company.

## ❌🧠 The real miss opportunity in a remote team, knowledge sharing
In a remote team, we don’t have regular random opportunities to come together like we would in a physical office. Conversations will be focused within your current team conversation channel. You won't be able talk over the watercooler/coffee machine about your current issues with someone else than your core team. You'll miss opportunities to talk with other teams about their challenges, bring up your expertise, and learn from someone else experiences/advices from an other team. We stop learning as much as we could because we're not seing each other anymore. 

As a remote company, how can you overcome this challenge? How do you optimize knowledge sharing, no matter which timezone?
This is where the concept of regular snackchats at Buffer was born 3 years ago, introduced by [Sunil](https://twitter.com/sunils34/).


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
- Your busy teammates will be able to see them at x2 speed
- Have a directory (notion/wiki) for future reference
- Like video call, putting a face, it's great to have a human touch to something "technical" to see someones smilling, worrying. 

#### The downsides of a Snackchat
The downside of snackchat is that takes quite a bit of energy to prepare. There can also be intimidating to ask if a topic you might want to present won't get enough interest from your workmates.
In a remote setting, people will try to make the best use of their time, and we might most of the time be busy on prioritties. The time you will set might not be the best fit for everyone. I wasn't able to participate to most of the snackchats because I live in a total different timezone than most of the people in the company. The tip here is to **make sure to record your snackchat** and repost it for people who couldn't attend them.

## ⚡️ Impromptu Knowledge Screencasts
An other format I personally enjoy doing is the "spontaneous" knowlege sharing with a screencast . I'm in the infrastructure team, where product engineers might not necessarly need to understand what happens "behind the scene", but where the knowledge could be useful to understand more how service bahave, or simply can pick their curiosity for learning purpose. 

I especially enjoy the screencast format for few reasons: 

- Snackchats requires preparations, and I know I will not be great at "live" presentations
- Being in a timezone where you wake up when others start going to sleep isn't great for coordinating any live presentation.
- I'm more in the introvert side.  It require quite a bit of energy to ask interests, worrying if people shows up. Sharing when I feel like it is easier mentally.
- My envy to create educative content isn't always consistent. There is some days where I will be more encline to share it and some where I'll not feel like it.

#### Tips on making "Impromptu Knowledge Screencasts" 
- I like using [Loom](https://www.loom.com). They make recording your screen and voice really easy. It also allows you to pause the recording, and aslso has an impressive online editor to trim your blanks.
- Try to keep the video dynamic, go to the point, and avoid the fluff, but keep the jokes
- Keep it short, ideally under 10 minutes
- When I know a video will be valuable on the long term, I try to do some Google slide to structure the video

Here an example where I wanted to show (not the first time) the benefits of using one of our internal librarie to make debuguing faster and easier: 
<div style="position: relative; padding-bottom: 62.5%; height: 0;"><iframe src="https://www.loom.com/embed/4a8605bdc5674ad3a551a37bfac09f3a" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## 📼 Use GIF to share knowledge
1 picture is worth a thousand words, but 1 GIF worth a lot more. It can save you or your teammates a lot of time, save you some context switching, and save your productivity. When someone has a question, or you want to explain something complicated, a simple GIF of the solution will be more than enough than trying to make on a call and explain it.

I enjoy using [cloudapp](https://www.getcloudapp.com/). For example here what I'll share when I wanted to share the results after migrating a service from PHP to Golang:

![PHP vs Golang CPU usage](/img/go-vs-php-cpu.gif) 

## 🥇 Make sharing knowledge explicitely valuable
At Buffer, we have an [engineerig framework](https://docs.google.com/spreadsheets/d/1k_QkZISJ2cIk_Py_pdzsAt5fUwWOYZVkkXg4KZM8IXA/htmlview) that encourage kowledge sharing. To reach a "Senior Engineer 2", One of the criteria would be... "educates across domain" or "Reach out to other teams within and beyond Buffer to share knowledge". I don't mean that money should be the incentive, but , I've personally because it was one of the condition to reach the next step, but then started to enjoy it more and more. I'm now doing it because I see value in it now whe other teamate tells me how valuable are my videos.

An other great way to encourange to continue sharing is to reach people who share that their knowledge were helpful. Here for example [Jose](https://josemdev.com) telling me he is using my video for a future mongoDB upgrade: 

![MongDB upgrade Jose watch](/img/jose-watch-eric-loom.jpg) 


## 👨‍🏫 Be a teacher, don't make asssumptions, over communicate

In a remote team, informations get easily lost. Other team members might not have the same context as you, new hires are recurrent occurence, and won't dare to ask ["stupid questions"](https://en.wikipedia.org/wiki/No_such_thing_as_a_stupid_question). 

Extra communication is key, don't make assumption, the more you say, the better teamates will get more knowledge. I've even more for trivial questions, where some fundamental might be missing and where your informations will be be really valuable 

One of the favorite people I've been working at Buffer is certainly [Colin](https://twitter.com/colinscape). Since day 1 I've joined the company, he's been relentlessy explaining and giving context if any issues or questions arises. He's been certainly the go to person when engineers has doubts or need advices. Indirectly, it help to make you look "approachable" for new members, especially in a remote settings where you won't have much chance to interract.  Sharing knowledge is definitely a great mark of leadership.

Additioanlly, It will help creating a great culture in your company where there no stupid question exists, and where your team will feel safe.

## ❤️ Share and re-share without limits
Sharing links via Slack or email are great, but those content get easily lost. You shouldn't make assumptions your teammates saw the video or message you've shared the other week. I recommend to maintain a directory (in Notion/Paper/Wiki etc...). When you see a question that was answered in one of your video, share it again. A natural snowball effect will happen when your teammates will see more and more people sharing their knowledge. 

Keep sharing ❤️


Over to you, what's your secrets on keeping your team in a remote setup? [Comment on Hacker News](https://news.ycombinator.com/item?id=24021103)


📚 Next read: [Why you should have a side project](https://erickhun.com/posts/why-you-should-have-a-side-project/)