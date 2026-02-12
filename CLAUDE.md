# CLAUDE.md

This repository contains Claude Code commands and skills.

## Workflow Rules

- Always plan before coding (`/plan` or `/build`)
- Use `/clear` after planning, before implementing
- Execute one step at a time (`/step N`)
- Verify after each change (tests, lint, types)

## Standard Flow

```
/overview → /plan "feature" → /clear → /step 1 → /clear → /step 2 → ...
```

## Token Optimization

- Read only necessary file sections
- Use `/clear` frequently
- One session = one task
- Summarize over verbose output
