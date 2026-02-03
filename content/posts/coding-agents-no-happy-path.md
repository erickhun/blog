+++
draft = false
date = 2026-02-03T10:00:00+08:00
title = "Your App Shouldn't Have a Happy Path"
description = "What if instead of coding the 'how', you described the outcome and let the agent figure it out?"
slug = ""
tags = ["ai", "agents", "product"]
categories = ["tech", "product"]
externalLink = ""
series = []
+++

What if instead of deciding what your app should do, you let it figure that out for each user?

There's something happening with coding agents right now that makes this possible. I'm not talking about ChatGPT or Claude apps you use every day. I'm talking about agents that have access to *tools* - they can browse your files, query databases, read documentation, hit APIs. They have all the context they need.

This isn't just "AI that answers questions." It's AI that *does things* - and figures out *how* to do them.

Most apps today use LLMs as fancy autocomplete. Summarize this text. Edit this image. Question in, answer out. The logic is hardcoded around a simple request-response pattern.

But what if instead of coding the "how", you just described the outcome you want and let the agent figure it out?

## The OpenClaw Pattern

[OpenClaw](https://openclawai.com/) is doing something wild. Users ask all kinds of crazy, unpredictable things - and it doesn't have hardcoded responses for each request. It has *tools* and decides which ones to use based on what you asked.

Let me write it again: 

**OpenClaw isn't programmed to handle every request. It's programmed to figure out how to handle any request.**

If a tool doesn't exist for something, someone adds it - and suddenly OpenClaw can do that thing too. No new "feature" code needed. Just a new capability the agent can choose to use.

This is a fundamentally different way to think about software:

- **Traditional**: Developer decides the happy path → user follows it
- **Agent-native**: User states what they want → agent figures out the path

Here's the reframe I think is powerful:

- Traditional app thinking: **"Did user use feature X?"**
-  Agent-native thinking: **"Did user achieve outcome Y?"**


X is finite. Y is **infinite**.  🤯

## How I Applied This

I'd been using this pattern for months without realizing it - [Connecting Obsidian with Claude (Desktop)](/posts/partner-os-claude-mcp-obsidian/) but then building a bot at [Buffer](buffer.com) with tools (git) that could grab source code and answer questions autonomously across all source code:

![Asking a coding agent about our source code](/img/coding-agents-no-happy-path/early-bot-question.png)

Then [Brandon](https://x.com/bkase_) sent me [The Agent-Native Architecture](https://every.to/guides/agent-native) from Every.to, and conversations with [David](https://x.com/cryptodavidw) pushed my thinking further. That article helped consolidate these thoughts into a clearer framework. 

The problem I faced: how do you surface signals from thousands of Slack messages without drowning in noise?

The old way would be hardcoded rules. "5 messages about the same topic = alert." "Keyword 'bug' + keyword 'production' = urgent." Threshold logic. Keyword matching.

I didn't do that.


Instead, I gave the agent an objective: 

> **"Find signals worth spending time on."**


The agent decides what matters. It looks at who's reporting, how many people, which channels, whether we already alerted recently. I don't write that logic - **I just give it tools to query and store data, and let it be smart.**

Same for alerting. Instead of threshold rules, the objective is: 

> **"Only interrupt the team if it's truly worth their attention.,  People's attention is expensive.** 

The agent weighs that.

The architecture looks something like this:

1. Each time a new message comes in  **Classifier agent** (cheap, fast model) → "Is this noise or signal?"
2. Then  **Gatekeeper agent** (best model) → "Is this worth interrupting humans?"

These agents aren't following instructions. They're pursuing objectives I gave them and querying tools I give them to figure out how to achieve the outcome. 

![How the coding agent thinks](/img/coding-agents-no-happy-path/coding-agent-workflow.png)

And the result: 

![The bot deciding what's worth alerting](/img/coding-agents-no-happy-path/bot-result.png)

**The pattern: tools + objective, not instructions. Let the agent figure out the HOW.**



## The Limits (and Excitement?)

I won't pretend this is perfect. Models today still make mistakes, and if you rely only on this, you'll get some frustrated users. A practical approach: keep the "happy path" coded, but offer a second path where the agent shows what it *thinks* the user might want. As models improve, that second path could become the primary one.

But here's where it gets exciting. The agent can accomplish things you didn't explicitly design for. The flywheel (_Credit to [every](https://every.to/guides/agent-native)_):

1. Build with tools the coding agent can use
2. Users ask for things you didn't anticipate
3. Agent composes tools to accomplish them (or fails, **revealing a gap**)
4. You observe patterns in what's being requested
5. Add tools or tune prompts to make common patterns efficient
6. Repeat


You're not shipping features anymore. You're expanding capabilities.

Agent-native architecture has consequences for how products *feel*, not just how they're built. The product becomes **less predictable but more useful**. You stop designing for the "average user" and start enabling any user's path.

The tricky part is tuning the agent's discretion. In my Slack bot, missed signals meant not enough direction. Wrong tool calls meant I needed more precision. It's a lot about finding the right balance - not too prescriptive in your prompts, not adding too many examples, or the agent leans too hard in one direction. I suspect we'll see prompt engineering become a real discipline (we're already seeing it). People who understand the limits and possibilities of each model and tune them accordingly.

## The Takeaways?

Stop telling your application what to do, just give them objectives. And let the agent judge and interpret what's best for the user. 

Software is getting exciting again. And we're about to see crazy things coming.

---

**If you want to build this yourself:**
- [pi-mono](https://github.com/badlogic/pi-mono) - The framework OpenClaw uses, by [badlogic](https://github.com/badlogic)
- [Claude Agent SDK](https://platform.claude.com/docs/en/agent-sdk/overview) - Anthropic's toolkit for building coding agents
-  I'm applying this agent-native architecture to [CrafMyGame](https://craftmygame.com) - to allow everyone to build their own games. It's not live yet, but if you're curious, sign up to get notified when it launches or try some games you can make there.

**People to follow:** [Dan Shipper](https://x.com/danshipper) wrote the Every.to article that consolidated this concept. [Brandon](https://x.com/bkase_) and [David](https://x.com/cryptodavidw) are both building AI-native products right now - all worth following if you're interested in this space.

*Have you experimented with agent-native patterns? I'm curious what you're building.*
