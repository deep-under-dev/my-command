# Codebase Onboarding Skill

## Purpose
Help new contributors understand and navigate an unfamiliar codebase quickly.

## Onboarding Checklist

### 1. Project Overview
- [ ] Read README.md
- [ ] Identify tech stack (package.json, requirements.txt, go.mod, etc.)
- [ ] Understand project structure
- [ ] Find contributing guidelines

### 2. Architecture Understanding
- [ ] Identify entry points (main, index, app)
- [ ] Map core modules/packages
- [ ] Understand data flow
- [ ] Find configuration files

### 3. Development Setup
- [ ] Clone and install dependencies
- [ ] Set up environment variables
- [ ] Run tests
- [ ] Start development server

### 4. Key Files to Read First
```
README.md           # Project overview
CONTRIBUTING.md     # How to contribute
docs/               # Documentation
src/index.*         # Entry point
src/config/         # Configuration
tests/              # Test examples
```

## Quick Analysis Commands

```bash
# Project structure
tree -L 2 -I 'node_modules|.git|dist|build'

# Find entry points
grep -r "main\|entry" package.json

# List all routes/endpoints
grep -rn "app\.\(get\|post\|put\|delete\)" src/

# Find TODO/FIXME
grep -rn "TODO\|FIXME\|HACK" src/

# Count lines by file type
find . -name "*.ts" | xargs wc -l | tail -1
```

## Documentation Template

```markdown
# {Project} Developer Guide

## Quick Start
1. Clone: `git clone {url}`
2. Install: `{package manager} install`
3. Configure: `cp .env.example .env`
4. Run: `{start command}`

## Architecture
- `/src/core` - Core business logic
- `/src/api` - API routes
- `/src/db` - Database models

## Common Tasks
- Add feature: ...
- Fix bug: ...
- Add test: ...
```
