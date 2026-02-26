# Contributing to SEO Skills for Agents

We welcome contributions! This project is about capturing **SEO knowledge and best practices** in a structured format that AI coding assistants can understand and follow.

## Ways to Contribute

### 1. Improve Existing Skills

The easiest way to start:

- **Fix outdated information** — SEO evolves quickly. If you spot something that's changed, open a PR.
- **Add missing edge cases** — Hit a gotcha? Add it to the "Failure modes" section.
- **Clarify procedures** — If a step confused you, make it clearer.
- **Expand references** — Add deeper documentation on specific topics in the `references/` directory.

### 2. Create New Skills

Have expertise in an SEO area we don't cover? Consider adding a new skill.

Before starting:
1. Check the existing `skills/` directory to avoid overlap.
2. Review the SKILL.md structure below.
3. Open an issue to discuss scope (optional but recommended).

### 3. Report Issues

Found a skill giving bad advice? Open an issue with:
- Which skill
- What went wrong
- What the correct behavior should be

## Skill Structure

Each skill follows this structure:

```
skills/<skill-name>/
├── SKILL.md              # Main instructions (short, procedural)
└── references/           # Deep-dive docs on specific topics (optional)
    └── *.md
```

### SKILL.md Sections

Every `SKILL.md` needs:

1. **YAML frontmatter** — `title`, `description`, `version`
2. **When to use** — Conditions that trigger this skill
3. **Inputs required** — What the AI needs to gather first
4. **Procedure** — Step-by-step instructions with code examples
5. **Verification** — How to confirm it worked
6. **Failure modes / debugging** — Common problems and fixes
7. **Escalation** — When to ask a human for help

## Guidelines

### Keep It Practical
- Focus on what developers actually need to do.
- Include concrete code examples, not abstract theory.
- Link to official docs for deep dives.

### Keep It Current
- Follow the latest search engine guidelines.
- Avoid deprecated patterns.

### Keep It Small
- Prefer small, focused skills over mega-skills.
- Keep `SKILL.md` short — push depth into `references/`.
- One skill should do one thing well.

## Submitting Changes

1. Fork the repo
2. Create a branch (`git checkout -b improve-schema-skill`)
3. Make your changes
4. Commit with a clear message
5. Open a pull request

---

*Your SEO expertise can help thousands of developers get better AI-generated code. Thank you for contributing!*
