# AGENTS.md

This file provides guidance to AI coding agents (Claude Code, Codex, Cursor, Copilot, etc.)
when working with this repository.

## Repository Overview

A collection of skills for AI coding agents. Skills are packaged instructions that extend
agent capabilities. Each skill lives in `skills/{skill-name}/` and follows the
[Agent Skills](https://agentskills.io/) format.

## Creating or Editing a Skill

### Directory Structure

```
skills/
  {skill-name}/           # kebab-case directory name
    SKILL.md              # Required: entry point (frontmatter + quick reference)
    rules/                # Atomic guidance, one rule per file (loaded on demand)
      _sections.md        # Section metadata (title, impact, prefix)
      _template.md        # Template for new rules
      {prefix}-{slug}.md  # Individual rule files
    AGENTS.md             # Full compiled guide (all rules expanded)
    metadata.json         # version, author, abstract
    README.md             # Maintenance notes
```

### Naming Conventions

- **Skill directory**: `kebab-case` (e.g., `building-with-ux`)
- **SKILL.md**: always uppercase, always this exact filename
- **Rule files**: `{prefix}-{slug}.md`; section is inferred from the prefix
- Files starting with `_` are special (templates/metadata, not rules)

### Best Practices for Context Efficiency

Skills load on demand — only the name and `description` load at startup; the full
`SKILL.md` loads only when the agent decides the skill is relevant.

- **Keep `SKILL.md` under 500 lines** — push detail into `rules/`.
- **Write a specific `description`** — it decides when the skill activates.
- **Use progressive disclosure** — `SKILL.md` links to rule files read only when needed.
- **File references work one level deep** — link directly from `SKILL.md` to `rules/`.

### End-User Installation

```bash
npx skills add <owner>/<repo> --skill {skill-name}
```

Manual (Claude Code):

```bash
cp -r skills/{skill-name} ~/.claude/skills/
```
