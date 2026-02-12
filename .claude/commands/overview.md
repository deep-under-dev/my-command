# /overview - Project Analysis

## Usage
```
/overview [path]
```

## Purpose
Quickly understand a codebase before making changes. Run this first when onboarding to a new project.

## Analysis Steps
1. Scan directory structure
2. Identify tech stack
3. Find entry points
4. Understand architecture
5. Locate build/test commands

## Output Format
```markdown
## Project Overview

### Tech Stack
- Language: ...
- Framework: ...
- Key dependencies: ...

### Structure
```
src/
├── components/  # UI components
├── services/    # Business logic
└── utils/       # Utilities
```

### Entry Points
- `src/index.ts` - Main entry
- `src/config.ts` - Configuration

### Architecture
[Brief description of how the system works]

### Commands
- Build: `npm run build`
- Test: `npm test`
- Dev: `npm run dev`

### Key Patterns
- [Pattern 1]
- [Pattern 2]
```

## Tips
- Save output to CLAUDE.md for future sessions
- Run before any major changes
- Use to onboard team members
