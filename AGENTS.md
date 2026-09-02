# AGENTS.md

Guidance for AI coding agents working with this repository.

## Repository overview

This repository contains installable skills for AI coding agents. Each skill lives in
`skills/{skill-name}/` and follows the [Agent Skills](https://agentskills.io/) format.

## Creating or editing a skill

### Directory structure

```text
skills/
  {skill-name}/
    SKILL.md              # Required entry point, routing, and workflow
    references/           # Focused guidance loaded directly from SKILL.md
      {topic}.md          # Complete instructions and checklists for one topic
    CONTRIBUTING.md       # Optional maintenance process
    metadata.json         # Optional version, author, abstract, references
    README.md             # Optional structure and maintenance map
```

`building-with-ux` uses seven pillar references. Its 60 rules are sections with stable rule IDs
inside those references; do not reintroduce one-file-per-rule fragmentation or another
duplicated all-rules document.

### Naming conventions

- Skill directories use `kebab-case`.
- The entry point is always uppercase `SKILL.md`.
- Reference filenames use descriptive `kebab-case`.
- Rule IDs use the pillar prefix and a kebab-case slug, for example
  `layout-group-and-rank-content`.

### Context efficiency

Only the skill name and description load at startup; `SKILL.md` loads when the skill is
relevant. Keep progressive disclosure shallow and predictable:

- Keep `SKILL.md` concise and procedural; move detailed guidance into references.
- Write a specific frontmatter description because it controls activation.
- Link every reference directly from `SKILL.md`; do not create chains of nested references.
- Group rules by the task-level context an agent needs, not merely to minimize line count.
- Keep one canonical copy of each rule and identify it with a stable ID.

### UX skill preservation requirements

When modifying `building-with-ux`:

- [ ] Preserve every existing rule's title, ID, impact, impact rationale, tags, source when one
  exists, instruction, examples, notes, and checks unless the change explicitly revises it.
- [ ] Keep the seven pillar agent checklists actionable and non-overlapping.
- [ ] Update counts and paths in `SKILL.md`, `README.md`, `CONTRIBUTING.md`, and `metadata.json`.
- [ ] Confirm all seven references are directly linked from `SKILL.md`.
- [ ] Check that each rule ID occurs exactly once across the references.
- [ ] Run the skill validator, link checks, metadata validation, and `git diff --check`.

### End-user installation

```bash
npx skills add <owner>/<repo> --skill {skill-name}
```

Manual installation for Claude Code:

```bash
cp -r skills/{skill-name} ~/.claude/skills/
```
