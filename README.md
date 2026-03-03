# Brandon's PM OS

A personal operating system for Claude Code — built for Product Managers who use AI to work faster, think clearer, and ship more.

Inspired by [Carl's Product OS](https://github.com/carlvellotti/carls-product-os). This is my own version, shaped around how I actually work: shipping AI side projects, writing about agentic AI, and building in public.

---

## What's Inside

| Folder | What it does |
|--------|-------------|
| `CLAUDE.md` | Entry point. Claude reads this at the start of every conversation. |
| `GOALS.md` | Your identity, ownership areas, and current quarterly goals. |
| `Tasks/` | Sprint tasks (active) and backlog. |
| `Projects/` | Active initiatives with specs and decision logs. |
| `Workflows/` | Repeatable processes with consistent inputs. |
| `Meetings/` | 1:1 notes, standups, and meeting notes. |
| `Knowledge/` | Reference materials, research, and notes on people. |
| `Templates/` | Reusable doc templates. |
| `Tools/` | Scripts and utilities. |
| `_Registry/` | System docs: MCPs, tools, tags. |
| `_temp/` | Scratch space and drop zone. |
| `.claude/skills/` | Slash commands — the power layer. |

---

## Slash Commands (Skills)

These are slash commands that activate specialized behaviors inside Claude Code. They make Claude feel like a second brain that knows your context.

### PM Workflow Skills

| Command | What it does |
|---------|-------------|
| `/standup` | Morning briefing. Surfaces today's priorities, blockers, and what to focus on. |
| `/weekly-update` | End-of-week reflection. Reviews what shipped, updates goal progress, drafts a summary. |
| `/new-post` | Starts a new Substack article. Helps outline, connects to existing research. |
| `/ship-check` | Pre-deploy checklist before pushing portfolio changes. |

### Utility Skills

| Command | What it does |
|---------|-------------|
| `/humanizer` | Removes AI writing patterns from text. Makes writing sound natural. |
| `/claudeception` | Extracts reusable knowledge from sessions and saves it as new skills. |
| `/frontend-design` | Generates polished, production-grade frontend components. |
| `/frontend-slides` | Creates animation-rich HTML presentations from scratch or converts PPT. |
| `/sql-queries` | Writes correct, performant SQL across Snowflake, BigQuery, PostgreSQL, etc. |
| `/install-claude-skill` | Installs a Claude Code skill from GitHub into a project. |

---

## Getting Started

### Option 1: Use the blank template

1. Copy `BLANK-OS/` to your working directory
2. Rename it or work from it directly
3. Fill in `CLAUDE.md` (your identity + context) and `GOALS.md` (your current goals)
4. Start a Claude Code session — Claude will read `CLAUDE.md` automatically

### Option 2: See a real example first

Browse `EXAMPLE-OS/` — this is my actual setup with real goals, tasks, and context. Use it as a reference, then customize `BLANK-OS/` to fit your work.

---

## Setting Up Skills

Skills live in `.claude/skills/` inside your project. Each skill is a folder with a `SKILL.md` file.

```bash
# From your project root, copy a skill:
cp -r path/to/brandons-pm-os/BLANK-OS/.claude/skills/standup .claude/skills/

# Or copy all skills at once:
cp -r path/to/brandons-pm-os/BLANK-OS/.claude/skills/ .claude/skills/
```

Then invoke them with `/skill-name` in Claude Code.

### Setting Up the Claudeception Hook (Optional but Recommended)

Claudeception auto-evaluates every session for extractable knowledge. To activate it:

1. Copy `.claude/hooks/claudeception-activator.sh` to your project's `.claude/hooks/`
2. Make it executable: `chmod +x .claude/hooks/claudeception-activator.sh`
3. Add to your `.claude/settings.json`:

```json
{
  "hooks": {
    "UserPromptSubmit": [
      {
        "hooks": [
          {
            "type": "command",
            "command": ".claude/hooks/claudeception-activator.sh"
          }
        ]
      }
    ]
  }
}
```

---

## Setting Up MCPs (Optional)

MCPs (Model Context Protocol servers) give Claude direct access to your tools. See `_Registry/MCPs.md` for setup instructions for:

- **Notion** — Read/write pages and databases
- **Linear** — Read/write issues, projects, cycles
- **GitHub** — Read/write repos, PRs, code search
- **Slack** — Read channels, send messages

---

## The Core Philosophy

**CLAUDE.md is your contract.** Claude reads it at the start of every conversation. Keep it honest and up to date — it's the difference between Claude knowing your context and starting from zero.

**Context beats instructions.** The more Claude knows about your goals, current work, and how you think, the better it operates as a thinking partner. Feed it context upfront.

**Skills compound.** Every `/claudeception` session can produce a new skill. Over time, you build a library of behaviors that reflect how *you* work — not a generic AI assistant.

**Start minimal.** Use `BLANK-OS/` as-is. Don't over-engineer the folder structure. Add organization only when friction appears.

---

## About This OS

Built by [Brandon Khoo](https://brandonkhoo-portfolio.vercel.app) — PM focused on AI-powered products and agentic AI.

Writing about the future of AI agents at [Agent Goose on Substack](https://agentgoose.substack.com).
