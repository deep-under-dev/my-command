# Workflow Rules

## Core Principles

### 1. Plan Before Code
- Always run `/plan` or `/build` before implementing
- No coding without understanding the task
- Define success criteria upfront

### 2. Context Management
- `/clear` after completing each task
- `/clear` after planning, before implementing
- One session = one focused task
- Prevents context pollution and saves tokens

### 3. Step-by-Step Execution
- One step at a time
- Verify completion before next step
- Tests must pass before proceeding
- Use `/step N` for structured execution

### 4. Token Efficiency
- Read only what you need
- Modify only what's necessary
- Summarize over verbose explanations
- Use subagents for large explorations

## Standard Workflow
```
/overview           # Understand project (first time)
    ↓
/plan "feature"     # Create implementation plan
    ↓
[Review plan]
    ↓
/clear              # Save context
    ↓
/step 1             # Execute first step
    ↓
[Verify: tests, lint]
    ↓
/clear              # Save context
    ↓
/step 2             # Execute next step
    ↓
...repeat...
```

## Verification Checklist
After each change:
- [ ] Tests pass
- [ ] Lint passes
- [ ] Types check
- [ ] Build succeeds
