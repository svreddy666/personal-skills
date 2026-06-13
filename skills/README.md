# Skills

Each subfolder here is one Agent Skill for Claude Code.

## How to add a new skill

1. Create a kebab-case folder: `skills/<skill-name>/`.
2. Add a `SKILL.md` inside it (copy from [skill-template.md](skill-template.md)).
3. Fill in the frontmatter:
   - `name` — kebab-case, matches the folder.
   - `description` — what it does **and** when to use it (this drives auto-triggering).
4. Write the instructions as clear, numbered steps.
5. (Optional) Add `references/` for templates/examples and `scripts/` for helper code.

## Conventions
- File must be exactly `SKILL.md` (case-sensitive).
- No XML angle brackets in frontmatter.
- Keep `SKILL.md` focused; move long content into `references/` and link to it.
- One skill = one folder. Don't put multiple skills in one file.

## Make it available to Claude Code
Symlink the skill folder into your Claude skills directory:

```bash
ln -s "$PWD/<skill-name>" ~/.claude/skills/<skill-name>
```
