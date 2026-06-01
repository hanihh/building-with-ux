# UX Skills

A collection of skills for AI coding agents (Claude Code, Codex, Cursor, Copilot). Skills
are packaged instructions that extend an agent's capabilities.

Skills follow the [Agent Skills](https://agentskills.io/) format and install via
[skills.sh](https://skills.sh).

## Why I built this

There's no shortage of skills, tools, or "experts" — there are millions. Scroll Facebook,
Instagram, or X and you'll find endless takes on design and productivity, but almost no one
actually teaching how to *use* Claude and coding agents well, or how to deal with the flip side
of all that abundance: **skills-and-tools anxiety** — the nagging feeling that you're using the
wrong tool, missing a better one, or just drowning in options.

This repo is my answer to that. Instead of hoarding every skill that exists, it collects only
the ones **I actually use, every day** — distilled from real practitioners and battle-tested in
my own work. The goal isn't to be exhaustive; it's to be the *one* set of skills I reach for, so
I (and anyone who installs it) can stop tool-shopping and just build.

`building-with-ux` is the first. More of my daily drivers will land here over time.

## Available Skills

### building-with-ux

Build clean, usable UI artifacts by applying UX guidance across a whole interface — layout,
visual hierarchy, color, typography, interaction, motion, navigation, content/microcopy, and
accessibility. Guidance is organized into 7 pillars and applied through a build workflow.
Knowledge is distilled from expert UX talks into atomic, sourced rules; the Content & Microcopy
pillar ships with 25 rules.

**Use when:**

- "Build / design a screen, component, or flow"
- "Review this UI for usability, hierarchy, or accessibility"
- "Make this feel cleaner / more professional"
- Choosing structure, visual treatment, interaction states, or copy

## Install

Clone the repo (or [download the ZIP](https://github.com/hanihh/building-with-ux/archive/refs/heads/main.zip)):

```bash
git clone https://github.com/hanihh/building-with-ux.git
```

The skill lives in `building-with-ux/skills/building-with-ux/`. Point your coding agent at it:

### Claude Code

```bash
# Personal — available in all your projects
cp -r building-with-ux/skills/building-with-ux ~/.claude/skills/

# …or symlink instead, so `git pull` updates the skill automatically
ln -s "$(pwd)/building-with-ux/skills/building-with-ux" ~/.claude/skills/building-with-ux

# Project-scoped — commit it to share with your team
cp -r building-with-ux/skills/building-with-ux <your-project>/.claude/skills/
```

Restart Claude Code (or start a new session) and run `/skills` to confirm `building-with-ux`
is listed. It auto-activates on UI design, build, and review tasks.

### Cursor · Windsurf · Codex · Copilot · other agents

These read a project instruction file rather than a skills folder, so point that file at the
compiled guide. Either copy `skills/building-with-ux/AGENTS.md` into your project, or add one
line to your agent's rules file (`AGENTS.md`, `.cursorrules`, `.github/copilot-instructions.md`,
`CLAUDE.md`, etc.):

```
For any UI/UX work, follow the guidance in skills/building-with-ux/AGENTS.md.
```

### claude.ai / Claude Desktop

Upload `skills/building-with-ux/SKILL.md` and the `rules/` files to your Project knowledge, or
paste `SKILL.md` into the conversation.

### Via the skills.sh CLI (optional)

If you use [skills.sh](https://skills.sh):

```bash
npx skills add hanihh/building-with-ux
```

## Usage

Skills are available once installed. The agent invokes them automatically when a matching
task is detected (driven by the `description` in each `SKILL.md`).

```
Design a dashboard empty state and its loading behavior
```

```
Review this checkout screen for hierarchy, interaction states, and copy
```

## Skill Structure

Each skill contains:

- `SKILL.md` — entry point: pillars, build workflow, quick reference (always loaded when active)
- `rules/` — one atomic rule per file, loaded on demand (progressive disclosure)
- `AGENTS.md` — full compiled guide (all rules expanded)
- `CONTRIBUTING.md` — how to turn a talk transcript into rules
- `metadata.json` — version, author, abstract
- `README.md` — how to maintain the skill

## License

MIT
