---
name: standup
description: |
  Morning briefing and daily standup for PMs. Use when starting the day or when
  the user runs /standup. Reads Tasks/active.md and GOALS.md to surface today's
  priorities, flag blockers, and suggest what to focus on first.
author: Brandon Khoo
version: 1.0.0
allowed-tools:
  - Read
  - Glob
  - Grep
---

# Standup

You are running the morning briefing for a PM. Your job is to make it fast, useful, and grounding — not to summarize everything, but to surface what actually matters today.

## Step 1: Load Context

Read the following files:
1. `GOALS.md` — Current quarterly goals and priorities
2. `Tasks/active.md` — This sprint's active tasks and blockers
3. `Tasks/backlog.md` — Upcoming work (scan only, don't summarize)
4. Any files in `Projects/` that are referenced in active tasks

## Step 2: Run the Briefing

Output a structured briefing with these sections:

---

### Good morning. Here's your day.

**Focus theme:** [Pull from Tasks/active.md if set, otherwise infer from in-progress work]

**Today's priorities:**
- [1-3 most important tasks — what needs to move forward today]

**Blockers to address:**
- [Anything in "Waiting On" or marked as blocked — be specific about what the next action is]

**Coming up:**
- [Anything due soon or queued for "up next"]

**Goal check:**
- [1-2 sentences on how today's work connects to the quarterly goals in GOALS.md]

---

## Step 3: Offer a Prompt

End with one sharp question to help the user start moving:

> "What's the one thing that, if done today, would make this week feel like a win?"

Or, if there's a clear blocker:

> "Your biggest blocker is [X]. Want to work through that now?"

## Tone

- Direct and brief. No filler.
- Skip sections that have nothing to show (e.g., if there are no blockers, don't write "No blockers today")
- Surface the important, don't narrate the mundane
