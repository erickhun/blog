+++
draft = false
date = 2026-02-11T19:00:00+08:00
title = "When Your AI Coding Assistant Destroys Your Work"
description = "Claude Code ran git checkout and wiped my uncommitted changes. It couldn't recover them. Then Codex did - with git commands I'd never seen before."
slug = ""
tags = ["ai", "agents", "git"]
categories = ["ai", "dev"]
externalLink = ""
series = []
+++

I was in the middle of building a feature. Everything was fine, until Claude Code `Opus 4.5` started to doubt about itself:

```text
I need to check something - when I reverted, I may have lost your working changes.
```
And then: 

```text
I apologize - when I ran git checkout to revert my changes, I accidentally 
reverted  your original working code for the "Add Tags" modal as well. Your 
uncommitted changes  were lost
```

🥲


## Here the Raw Quotes

### What Claude said happened (verbatim)

[![Claude session showing the destructive checkout and failed recovery](/img/ai-coding-assistant-destroys-work/claude-session-summary.webp)](/img/ai-coding-assistant-destroys-work/claude-session-summary.webp)

```text
Session Summary. Commands I Ran

1. Exploration/Reading:
- Multiple Glob and Grep searches to find the tag editor code
- Read on bundle-wizard/index.tsx and bundle-wizard.module.css
- Chrome DevTools MCP: navigate_page, take_snapshot, wait_for, take_screenshot
2. Edits I Made:
- Edit on bundle-wizard.module.css - replaced tag editor CSS with my first redesign
- Edit on index.tsx - changed "Add Tags" to "Asset Details", restructured JSX for two-column layout
- Edit on __tests__/bundle-wizard.test.tsx - replaced all 'Add Tags' with 'Asset Details'
- Second Edit on CSS - replaced with retro game UI design (the one you didn't like)
3. The Destructive Command:
git checkout client/components/pages/bundle-wizard/bundle-wizard.module.css client/components/pages/bundle-wizard/index.tsx client/components/pages/bundle-wizard/__tests__/bundle-wizard.test.tsx
3. This reverted all 3 files to HEAD, losing your original uncommitted tag editor code.
4. Recovery attempts:
- git stash list, git stash show, git fsck --lost-found - tried to find your lost changes

Context Size

I don't have direct visibility into the exact token count, but this conversation includes:
- ~2-3 large file reads (the TSX is 31k+ tokens alone, so I read portions)
- Multiple screenshots you provided
- Several CSS blocks (200+ lines each)
- The system automatically compresses older messages as we approach limits

What Was Lost

Your original tag editor implementation:
- tagEditorState state and logic in index.tsx
- All .tagEditor* CSS classes in the module CSS
- Test assertions referencing "Add Tags"

```

I've asked the same claude code conversation if it could  recover the work it just destroyed.

It couldn't.

Well, felt pretty bad, not because of what it was working on, but the uncommitted work I didn't commit. 


Then thanksfully, I've asked Codex 5.3 xhigh to try to recover it:

### Whatt Codex did

```text
Prompt:
Claude lost all my uncommitted change we've made. How can I retrieve them?

I’m going to do recovery triage first: check whether Git still has those edits in stash/index/reflog/dangling objects before we fall back to IDE local history. I’ll run only read-only recovery commands.

Ran git status --short
Ran git stash list
Ran git reflog '--date=iso' -n 30
Ran git stash show --name-only 'stash@{0}'
Ran git stash show --name-only 'stash@{1}'
Ran git diff --cached -- client/components/pages/bundle-wizard/bundle-wizard.module.css client/components/pages/bundle-wizard/index.tsx client/components/pages/bundle-wizard/__tests__/bundle-wizard.test.tsx
Ran git fsck --no-reflogs --lost-found --unreachable --no-progress
Ran git cat-file -p 28993afdac33853aa0e0bad5f47c30b3b6383726
Ran git cat-file -p 201f36ffde9aacc489646b72ebe15b7654102aed
Ran git cat-file -p b2df1a50a9356628daa0583cc4b8a484b4a8c634
Ran git cat-file -p 28993afdac33853aa0e0bad5f47c30b3b6383726 > client/components/pages/bundle-wizard/index.tsx
Ran git cat-file -p 201f36ffde9aacc489646b72ebe15b7654102aed > client/components/pages/bundle-wizard/bundle-wizard.module.css
Ran git cat-file -p b2df1a50a9356628daa0583cc4b8a484b4a8c634 > client/components/pages/bundle-wizard/__tests__/bundle-wizard.test.tsx
Ran npx jest client/components/pages/bundle-wizard/__tests__/bundle-wizard.test.tsx --runInBand

Recovered. I restored your lost uncommitted changes from Git’s unreachable blob objects.
Restored files:
- index.tsx
- bundle-wizard.module.css
- bundle-wizard.test.tsx
Validation:
- bundle-wizard.test.tsx --runInBand passes (58/58)
```

## My Interpretation

This is what happened:

1. I asked Claude Code to iterate on front-end files.
2. It ran `git checkout <file>...` to "clean up" changes.
3. That reset those files to `HEAD` and wiped uncommitted work.
4. It then failed to recover, and said it was lost.
5. Codex used a different strategy (`fsck` + `cat-file`) and recovered it.

I thought the context might have been too full, and it might have went off rails, but it was only half:

[![Claude Code context usage - only 58%](/img/ai-coding-assistant-destroys-work/context-size.webp)](/img/ai-coding-assistant-destroys-work/context-size.webp)

I've asked what Claude Code tried to do: 
```bash
Prompt: What was your intent when doing the git command?

My intent was to revert only my changes back to the state before I 
started editing.

I thought running git checkout on those files would restore them to  the version 
that  existed when we started the conversation - which I assumed was your working 
"Add Tags" modal.  My mistake: I didn't realize that your "Add Tags" modal code 
was itself  uncommitted/unstaged work.  The git checkout command reverts to the 
last committed state (HEAD), not to "the state before Claude started editing."

```

## What I Changed after that

The biggest lesson for me is not "LLMs are bad." The lesson is: **do not grant destructive permissions without guardrails.**

Capability and safety are different systems.

### 1. No destructive git action without a checkpoint

Before `reset --hard`, `checkout --`, `restore --source`, `clean -fd`, or rebases, snapshot current work:

```bash
mkdir -p .git/safety
ts=$(date +%Y%m%d-%H%M%S)

# tracked + staged changes
git diff > ".git/safety/working-$ts.patch"
git diff --staged > ".git/safety/staged-$ts.patch"

# untracked files (not included in git diff)
git ls-files --others --exclude-standard > ".git/safety/untracked-$ts.txt"
if [ -s ".git/safety/untracked-$ts.txt" ]; then
  tar -czf ".git/safety/untracked-$ts.tgz" -T ".git/safety/untracked-$ts.txt"
fi
```

You raeder might have a better one? 

### 2. git hooks are not enough

`pre-commit` hooks runs only on commit.
Most destructive actions happen outside commit.
The protection must run before destructive commands.

### 3. Commit and push more often

Small, frequent checkpoints are cheaper than memory-based reconstruction.

### 4. If one model says "impossible," try another

Different models explore different recovery paths.
In this case, that difference saved the work.

## Takeaways

I will still use LLMs every day. They improve my speed massively, probably by 2x to 5x. It also allows me to do things I could have never done before.

Also, I'm learning a lot watching coding agent do work, I didn't know about `fsck` + `cat-file` until today, so even uncommited work are still. recoverable. 

I trust AI for speed, its infinite knowledge, but not for safety. Safety is my job.

Right after this, I've asked Claude Code to do again the frontend change I probably would have never done if LLM didn't exist.


If folk at Antrhopic read that, ` Feedback ID: c7f9e357-28e4-48d0-99bb-5d0501c0c5ef` . Maybe they'd have better explanation on what happened. 

ps: I'm using `Opus 4.5` today because I was under the impression (probably wrong?) that `Opus 4.6` didn't perform as well after it upgraded. 
