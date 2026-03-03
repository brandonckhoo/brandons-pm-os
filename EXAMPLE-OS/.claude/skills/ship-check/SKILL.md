---
name: ship-check
description: |
  Pre-deploy checklist before pushing or publishing changes. Use when the user
  runs /ship-check or is about to deploy. Checks that content is current,
  changes are committed, and nothing obvious is broken before going live.
  Designed for portfolio sites and web projects but adaptable to any publish workflow.
author: Brandon Khoo
version: 1.0.0
allowed-tools:
  - Read
  - Bash
  - Glob
  - Grep
---

# Ship Check

You are running the pre-deploy checklist. The goal is to catch anything obvious before it goes live — not to be exhaustive, but to prevent embarrassing misses.

## Step 1: Ask What's Shipping

> "What are you about to deploy or publish? Give me a quick description of the change."

## Step 2: Run the Checklist

Adapt based on what's being shipped. Run relevant checks:

### For a portfolio or website change:

**Content checks:**
- [ ] Is the content source of truth up to date? (e.g., `src/content/site.ts` or equivalent)
- [ ] Are there any TODO comments or placeholder text left in?
- [ ] Are all links real (no broken hrefs, no `#` placeholders)?
- [ ] Are all images loading (no broken paths or missing files)?

**Code checks:**
- [ ] Are there any console.log statements left in?
- [ ] Does the build pass? (If applicable — offer to run `npm run build`)
- [ ] Are there TypeScript errors? (If applicable)

**Deploy checks:**
- [ ] Is the change committed and pushed to the right branch?
- [ ] Is there a deploy preview to verify? (Vercel, Netlify, etc.)

### For a Substack or article publish:

**Content checks:**
- [ ] Is the title final?
- [ ] Is the subtitle or preview text compelling?
- [ ] Are all links working and pointed to the right places?
- [ ] Is there a featured image or header?
- [ ] Have you read it out loud (or run it through `/humanizer`)?

**Publish checks:**
- [ ] Is the audience / visibility set correctly (public / subscribers only)?
- [ ] Is the publish date/time right?
- [ ] Is there a CTA at the end?

## Step 3: Surface Issues

For each check that fails or is unclear, flag it clearly:

> "⚠️ Found a potential issue: [description]. Want me to fix it?"

## Step 4: Give the Go/No-Go

After running checks:

**If clean:**
> "Looks good. Ship it."

**If issues found:**
> "Found [N] thing(s) to address before shipping. Want to go through them now?"

## Tone

- Fast. This is a checklist, not an audit.
- Direct about issues. Don't soften or hedge.
- Trust the user — if they say it's fine, it's fine.
