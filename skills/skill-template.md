# SKILL.md Template

Copy the block below into `skills/<your-skill>/SKILL.md` and fill it in.

```markdown
---
name: your-skill-name
description: What the skill does. Use when [specific trigger conditions — the situations where Claude should reach for this].
---

# Your Skill Name

One-line statement of what this skill helps accomplish.

## Instructions

### Step 1: [First major step]
Clear explanation of what to do.

### Step 2: [Next step]
...

### Step N: Produce the output
Describe the final deliverable. If it uses a template, link it: [references/template.md](references/template.md).

## Principles
- Key rule or quality bar to hold to.
- Another guiding principle.
```

## Tips
- **`description` is the most important field** — it's what Claude uses to decide *when* to trigger the skill. Be specific about both the task and the trigger.
- Keep `SKILL.md` lean. Put long templates, examples, or reference material in a `references/` folder and link to them.
- Use numbered steps for anything procedural — they make the skill reliable to follow.
- Folder name and `name:` should match, in kebab-case.

## Optional structure
```
skills/your-skill-name/
  SKILL.md            # required
  references/         # optional: templates, examples, docs
  scripts/            # optional: helper scripts
  assets/             # optional: static files
```
