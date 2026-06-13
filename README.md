# Personal Skills

A personal collection of **Agent Skills** for Claude Code (and compatible AI coding agents).

A skill is a folder of instructions and resources that Claude loads on demand to perform a specialized task in a repeatable way. Each skill lives in `skills/<name>/` and contains a `SKILL.md` with YAML frontmatter (`name`, `description`) plus Markdown instructions.

## Structure
- `skills/<skill-name>/SKILL.md` — the skill itself (instructions + frontmatter).
- `skills/<skill-name>/references/` — optional templates, examples, and docs the skill links to.
- `skills/<skill-name>/scripts/` — optional helper scripts the skill can run.
- [skills/README.md](skills/README.md) — how to add and structure a skill.
- [skills/skill-template.md](skills/skill-template.md) — copyable `SKILL.md` template.

## Skills
- [decision-making](skills/decision-making/SKILL.md) — turn messy input into a structured leadership decision doc (options, tradeoffs, recommendation, reversibility).

## Using a skill
Make a skill available to Claude Code by placing (or symlinking) its folder into `~/.claude/skills/`:

```bash
ln -s "$PWD/skills/decision-making" ~/.claude/skills/decision-making
```

Then invoke it in Claude Code with `/decision-making`, or just describe the task and Claude will trigger it based on the `description`.

## Writing good skills
- Make the `description` specific about **what it does AND when to use it** — that's how Claude decides to trigger it.
- Keep `SKILL.md` focused on core instructions; put long templates/examples in `references/`.
- Folder names are kebab-case; the file must be exactly `SKILL.md`.
