---
name: exploration
description: Explore and understand before coding
---

# Explore First

## Why It Matters
Jumping straight to coding produces code that solves the wrong problem. Understanding comes first.

## The Four Phases (Claude Code Best Practices)

### Phase 1: Explore
- Read relevant files
- Understand existing patterns
- Check how similar features work
- Identify dependencies

### Phase 2: Plan  
- Break into small steps
- Define changes per file
- Set verification criteria
- Identify risks

### Phase 3: Confirm
- Share plan with user
- Get feedback
- Adjust as needed
- Then `/clear` to save context

### Phase 4: Implement
- Follow the plan
- One step at a time
- Verify each step
- `/clear` between steps

## Asking Good Questions
When onboarding to a codebase:
- "How does logging work?"
- "How do I add a new API endpoint?"
- "Why does this call foo() instead of bar()?"
- "What edge cases does this handle?"

## Using Plan Mode
- Use for exploration/planning (read-only)
- Switch to normal mode for implementation
- Separates thinking from doing

## Reference Existing Patterns
**Bad:** "add a calendar widget"
**Good:** "look at how HotDogWidget.php implements widgets. Follow the same pattern for a calendar widget."
