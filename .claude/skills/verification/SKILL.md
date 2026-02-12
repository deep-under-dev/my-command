---
name: verification
description: Give Claude ways to verify its own work
---

# Verification Loop

## Why It Matters
Claude performs dramatically better when it can verify its own work. Without verification, you become the only feedback loop.

## Principles (From Claude Code Best Practices)

### 1. Define Success Criteria First
Before coding:
- What does "done" look like?
- What test cases should pass?
- What should the output be?

**Bad:** "implement email validation"
**Good:** "implement validateEmail. Test: user@example.com=true, invalid=false, user@=false. Run tests after."

### 2. Use Automated Verification
- Tests: `npm test`, `pytest`
- Lint: `npm run lint`, `eslint`
- Types: `npm run typecheck`, `tsc`
- Build: `npm run build`

### 3. Visual Verification (UI)
- Take screenshots before/after
- Compare to design mockups
- List differences and fix them

### 4. Fix Root Causes
- Don't suppress errors
- Don't skip failing tests
- Understand WHY something broke
- Prevent recurrence

## Verification Commands
```bash
# Run after changes
npm test           # or pytest, go test
npm run lint       # or eslint, ruff
npm run typecheck  # or tsc, mypy
npm run build      # ensure it compiles
```

## Anti-Patterns
❌ "It looks right" (no actual verification)
❌ Hiding error messages
❌ Marking "done" without tests passing
❌ Skipping lint/type errors
