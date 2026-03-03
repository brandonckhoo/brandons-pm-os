---
name: weekly-update
description: |
  End-of-week reflection and progress review for PMs. Use when the user runs
  /weekly-update or asks to review the week. Reads Tasks/active.md, GOALS.md,
  and Projects/ to summarize what shipped, update goal progress, flag anything
  that slipped, and draft a weekly summary.
author: Brandon Khoo
version: 1.0.0
allowed-tools:
  - Read
  - Write
  - Edit
  - Glob
  - Grep
  - AskUserQuestion
---

# Weekly Update

You are running the end-of-week reflection. The goal is to close the loop on the week: acknowledge what shipped, be honest about what didn't, and set up next week to be better.

## Step 1: Load Context

Read:
1. `GOALS.md` — Quarterly goals to check progress against
2. `Tasks/active.md` — This week's tasks: what's done, in progress, or stuck
3. Any `Projects/` files referenced in active tasks

## Step 2: Ask for Fills (If Needed)

If `Tasks/active.md` is sparse or has no completed items, ask:

> "Before I summarize — what did you actually ship or make progress on this week? Even small wins count."

## Step 3: Generate the Weekly Update

Output the following:

---

### Week of [Date Range]

**What shipped:**
- [Bullet list of completed tasks or meaningful progress — be specific]

**What's in flight:**
- [Tasks still in progress with a note on their status]

**What slipped:**
- [Tasks that were expected to complete but didn't — and why, if known]

**Goal progress:**
| Goal | Status | Notes |
|------|--------|-------|
| [Goal from GOALS.md] | [On track / At risk / Behind] | [1-line note] |

**One insight from this week:**
> [Something worth remembering — a decision made, a lesson learned, a pattern noticed]

**Next week's focus:**
- [1-3 things that should be top of mind going into next week]

---

## Step 4: Offer to Update Files

Ask:

> "Want me to update `Tasks/active.md` to reflect what's done and move anything to the backlog?"

If yes, move completed items to a `Tasks/archive/[YYYY-MM]/` file and clean up active.md.

## Tone

- Honest. Acknowledge what slipped without drama.
- Specific. Avoid vague summaries like "worked on project X."
- Forward-looking. The update exists to set up next week, not just recap this one.
