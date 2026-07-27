+++
draft = true
date = 2026-07-14T11:30:00+08:00
title = "What Is an AI Agent, Really?"
description = "Everyone is building agents. Almost nobody can define one. Here's the anatomy of an AI agent, and where Claude Code, Claude Opus 4.6, Codex or ChatGPT fit in it."
slug = ""
tags = ["ai", "agents"]
categories = ["tech"]
externalLink = ""
series = []
+++

Quick quiz. Is ChatGPT an AI agent? Is Claude Opus 4.6 one? Is Claude Code? And when my hairdresser tells me the dating app they're building "runs on agents"... is that one too?

If you hesitated on any of these, this post is for you. (For the impatient: sort of, no, yes, and it depends - we'll get there.)

"Agent" might be the most abused word in tech right now. Your bank announced one. Every SaaS added an "AI agent" tab. ChatGPT has an agent mode. Your IDE has an agent panel. Same word, five different things - and nobody stops to define it. It reminds me of "cloud" in 2010, or everything becoming "AI-powered" a few years ago.

So here's the definition I use:

> **An agent = a brain, hands, and a loop.**

- **The brain** is the model (Claude Opus 4.6, GPT-5.6 sol, Gemini 2.5 Flash). It reasons, plans, and decides. But alone, it's just text in, text out.
- **The hands** are the tools: read files, run code, browse the web, send messages. This is how the brain touches the world.
- **The loop** is what makes it an *agent*: it acts, looks at the result, and decides what to do next. Again and again, until the job is done.

A chatbot answers you once. An agent keeps going. You don't guide every step - you give it a goal.

For the techies: the brain is the only part that thinks. Everything wrapped around it is regular software, the kind we've been writing for decades. That wrapper is called the **harness**, and for most purposes, the harness *is* the agent.

## What's NOT an agent

Here's the thing: most "AI-powered" apps today are not agents. They're a single API call to a model.

Summarize this article. Categorize this support ticket. Write a product description. One prompt goes to the brain, the answer comes back, done. No hands, no loop. In [Your App Shouldn't Have a Happy Path](/posts/coding-agents-no-happy-path/) I called this "fancy autocomplete" - useful, but it's a feature, not an agent.

There's actually a ladder:

1. **One API call**: question in, answer out. Most AI features live here.
2. **A chatbot**: same thing, but it remembers the conversation. Still just words.
3. **A workflow**: code chains several model calls in a fixed order. "Transcribe, then summarize, then translate, then email it." Looks smart, but the path is hardcoded. The model fills in the blanks, it doesn't choose the route.
4. **An agent**: the model chooses the route. Tools + loop, pointed at a goal.

The litmus test is one question: **who decides the next step?** If your code always knows what happens next, it's a workflow. If the model gets to choose, you're in agent territory.

One refinement, because it trips people up: choosing isn't picking. Plenty of workflows let the model pick between branches - "is this ticket a complaint or a refund? route it accordingly". Still a workflow: the model picks between routes *you* drew. It becomes an agent when the model draws the route itself.

That ladder also answers the first quiz question. ChatGPT was born a chatbot, step 2: it just talked. Over time it grew tools, browsing, and an agent mode. Today it sits somewhere between step 2 and step 4 depending on what you ask it to do. Hence: "sort of".

Nothing wrong with the lower rungs, by the way. A workflow is often the right choice: cheaper, predictable, easier to debug. And in practice you rarely pick just one rung - real systems mix them. An agent can trigger one of your fixed workflows as a tool; a workflow can hand its messiest step to a small agent ("figure out why this failed"). It's a dial, not a switch - the ladder classifies decisions, not products.

## The loop is where the magic happens

The litmus test says the model decides the next step. What does that actually look like?

Say you tell an agent: "book me a table for four tonight, somewhere quiet."

1. It searches for restaurants nearby. Finds ten.
2. It checks the reviews and filters out the loud ones.
3. It tries to book the best one. Fully booked.
4. It moves to the second choice, books it, and sends you the confirmation.

Nobody wrote that sequence down. Somebody *did* write a lot - the system prompt, the tool list, maybe a house rule like "always confirm before paying". But that's the rules of the game, not the moves. No line of code says "search, then filter, then book, then fall back". The model improvised the route at runtime, one step at a time: act, observe, decide, repeat. That's the loop.

Step 3 is the moment that matters. The restaurant was full. A workflow survives that only if a developer saw it coming and coded "if full, try the next one". Nobody saw this one coming - and the agent didn't need them to. It hit a wall, looked at it, and walked around it. The developer's foresight went into the tools and the instructions, not into an if/else for every wall the agent might meet.

That's what you're really buying with an agent: not smarter answers, but a smarter *path*.

## "Claude" is three different things

Part of the confusion is naming. When someone says "Claude", they might mean three completely different layers:

1. **The model**: Opus 4.6 (or Sonnet 4.5, or Haiku 4.5). A giant neural network that takes text in and produces text out. That's it. A model alone can't read your files or browse the web. It's a brain in a jar.
2. **The agent**: Claude Code, or the Claude Desktop app. Software built *around* the model that gives it tools, memory, and a loop.
3. **The company**: Anthropic, who makes both.

Two more quiz answers right there. Is Opus 4.6 an agent? No: it's a brain in a jar, no hands, no loop. Is Claude Code an agent? Yes: it's that same brain, given hands and a loop.

Same on the other side of the fence: GPT-5.6 sol is a model, ChatGPT is a general-purpose agent built around it, and Codex is a coding agent built around it. OpenAI is the company.

Google went for maximum confusion: Gemini 2.5 Flash is a model, Gemini is *also* the app (the agent), and Gemini CLI is the coding agent. One name, three layers.

Once you see this separation, a lot of AI news suddenly makes more sense.

## The anatomy of an agent

So an agent is a brain with things wrapped around it. But what exactly do you wrap around a brain to turn it into an agent? Let's open one up, layer by layer, from the bottom:

[![The anatomy of an AI agent](/img/what-is-an-ai-agent/agent-stack.png)](/img/what-is-an-ai-agent/agent-stack.png)

### 1. The model

Every agent starts with a model. Big one, small one, doesn't matter. Claude Opus 4.6, GPT-5.6 sol, Gemini 2.5 Flash, or an open-source model running on your laptop. This is the intelligence, the part that reasons and decides. Everything else in the stack exists to feed it and to act on its behalf.

### 2. The system prompt

The system prompt tells the model what its role in the universe is. "You are a coding assistant. You are careful. You ask before deleting things." It's the job description. Two agents can use the exact same model and behave completely differently just because of their system prompts.

### 3. Tools

This is what separates an agent from a chatbot. Tools are the things the agent can actually *do*: read files, run terminal commands, query a database, browse the web, send a message. The model doesn't execute anything itself - it says "I want to run this command", and the harness (the hands!) executes it and feeds the result back.

I wrote about how powerful this becomes in [Your App Shouldn't Have a Happy Path](/posts/coding-agents-no-happy-path/): give an agent tools and an objective, and it figures out the "how" itself.

### 4. Skills

Skills are basically documentation. A skill is a markdown file that teaches the agent how to do something complex: "here's how we deploy", "here's our code review checklist", "here's how to write a good commit message". The agent reads it when relevant, like a new employee reading the company wiki. Simple, but effective.

### 5. MCP

MCP (Model Context Protocol) sounds scarier than it is. Think of it as a bridge that lets an agent talk to the outside world: your Gmail, your Notion, your Figma, your file system. In practice, MCP has mostly become a way to distribute *tools* - a standard plug so that any app can offer its capabilities to any agent.

I use it to [connect Claude to my Obsidian notes](/posts/partner-os-claude-mcp-obsidian/), and that single bridge changed how I use AI daily.

### 6. Messages

Finally, the conversation itself. Everything you've said, everything the agent answered, every tool result. This all gets replayed to the model on every single turn - the model has no memory of its own.

## Here's the part most people miss

Look at that stack again. The system prompt, the tools, the skills, the MCP servers, the messages... **almost everything above the model is just context.**

There's no database of skills inside the model. No plugin system in the neural network. On every turn, the agent takes all of it - job description, tool list, documentation, conversation history - stuffs it into one giant text prompt, and sends it to the model.

That's the whole trick. An agent is a model being fed really, really good context, inside a loop, by deterministic software.

It also explains a real limitation: context is finite. Install 5 MCP servers and a few skills, everything works great. Install 50, and your agent gets *worse* - it drowns in its own context. More on that in a future post.

## So where does everything fit?

Let's place the famous names on the map. The three-layer split from earlier turns the mess into a tidy grid:

| | Anthropic | OpenAI | Google |
|---|---|---|---|
| **The model** | Opus 4.6, Sonnet 4.5, Haiku 4.5 | GPT-5.6 sol | Gemini 2.5 Pro, 2.5 Flash |
| **General-purpose agent** | Claude Desktop / claude.ai | ChatGPT | Gemini (the app) |
| **Coding agent** | Claude Code | Codex | Gemini CLI |

Every company ships the same three layers - and now you can see exactly where Google reused a name.

There's also a whole family the grid can't hold: agents that ship the harness *without* the brain. You plug in whichever model you like:

| Name | What it is | The brain |
|---|---|---|
| Cursor | Coding agent inside an editor | Your pick: Claude, GPT, Gemini... |
| OpenClaw | Open-source general-purpose agent | Bring your own |

If you ever doubted that the model and the agent are separate layers, there's the proof: the wrapper alone is a product.

A rule of thumb: **if it's a name you pay per token, it's a model. If it's a thing that does stuff for you, it's an agent.**

And my hairdresser's dating app? Honest answer: **it depends how they built it** - and from the outside, you can't tell.

If the AI just answers messages, easy: chatbot with a nice prompt. But even the impressive version - matching people, planning the date, booking the restaurant - could be built two ways:

- **Their code runs a fixed pipeline** - match, then plan, then book - and the model fills in the blanks at each step. That's a workflow with good marketing.
- **The model draws the route itself** - picks the spot, hits a fully-booked restaurant, tries another. *That's* an agent.

Same features on the screen, different machinery underneath. The label isn't about what the app does; it's about who decides the next step.

## The takeaways

- An agent = a brain, hands, and a loop. The model thinks, the harness acts.
- Most "AI-powered" apps are a single API call or a hardcoded workflow. The litmus test for an agent: does the model pick between routes you drew, or draw the route itself?
- "Claude" the model (Opus 4.6) and "Claude" the agent (Claude Code, Claude Desktop) are different layers. Same for GPT-5.6 sol vs ChatGPT vs Codex.
- Tools are what turn a chatbot into an agent. Skills and MCP are just ways to feed it more capabilities.
- Almost everything is context. The quality of an agent is mostly the quality of what you feed the model.

During the industrial revolution, we learned to harness energy with machines. This time, we're learning to harness intelligence with agents. Might be worth knowing what's inside one.

---

**Liked it?**  I'm building [heylife](https://heylife.ai/), an agent that helps you to get ready for anything on your calendar.  It prepares you for every calendar event. As each one gets closer, it sends guidance at each stage, when it can actually help. You never have to remember to ask. 


**Next reads**:

- [Your App Shouldn't Have a Happy Path](/posts/coding-agents-no-happy-path/)
- [Connecting my Raw Thoughts to Claude with Obsidian](/posts/partner-os-claude-mcp-obsidian/)
- [When Your AI Coding Assistant Destroys Your Work](/posts/when-your-ai-coding-assistant-destroys-your-work/)

*Are you building agents? I'm curious what definition you'd give.*
