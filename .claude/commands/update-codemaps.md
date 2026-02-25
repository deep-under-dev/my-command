# /update-codemaps - Auto-Generate Codebase Maps

## Usage
```
/update-codemaps [scope]
```

### Scopes
- Full: `/update-codemaps` (entire repo)
- Directory: `/update-codemaps src/`
- Module: `/update-codemaps src/auth/`

## Purpose
Generate and update codebase maps that help understand project structure.
Creates/updates CODEMAP.md files with architecture overview.

## Flow

```
┌─────────────────────────────────────────────────────┐
│  /update-codemaps                                   │
├─────────────────────────────────────────────────────┤
│  1. SCAN       │ Walk directory structure           │
│  2. ANALYZE    │ Identify modules, dependencies     │
│  3. MAP        │ Create visual/textual map          │
│  4. DOCUMENT   │ Add descriptions per component     │
│  5. SAVE       │ Write CODEMAP.md                   │
└─────────────────────────────────────────────────────┘
```

## Output Format
```markdown
# CODEMAP.md

## Architecture Overview
[High-level diagram]

## Directory Structure
src/
├── auth/        # Authentication & authorization
├── api/         # REST endpoints
├── db/          # Database models & migrations
└── utils/       # Shared utilities

## Key Files
- src/index.ts   # Entry point
- src/config.ts  # Configuration

## Dependencies
[Module dependency graph]
```

## Benefits
- Faster onboarding for new contributors
- Better context for AI assistants
- Living documentation that stays current
