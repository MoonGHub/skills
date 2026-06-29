# Codex Skills

Personal agent skills repository.

## Available Skills

- `project-ai-context-builder`: Analyze a repository and create or refresh `AI_CONTEXT` and `AGENTS.md` documentation for AI-driven development continuity.

## Quality Notes

- Review record: `docs/project-ai-context-builder-audit.md`
- Runtime quality checklist: `skills/project-ai-context-builder/references/quality-check.md`

## Install With `npx skills`

```bash
npx skills add MoonGHub/skills --skill project-ai-context-builder
```

## Install With Codex `skill-installer`

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo MoonGHub/skills \
  --path skills/project-ai-context-builder
```

Restart your agent app after installing if newly installed skills are not detected immediately.
