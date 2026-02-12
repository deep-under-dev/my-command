# /plan - Implementation Planning

## Usage
```
/plan "feature or task description"
```

## Purpose
Create a detailed implementation plan WITHOUT writing code. Based on Claude Code's "Explore first, then plan, then code" principle.

## Steps
1. Analyze requirements
2. Explore relevant code
3. Break into small steps
4. Define verification for each step

## Output Format
```markdown
## Goal
[One-line summary]

## Understanding
- Current state: ...
- Required changes: ...
- Constraints: ...

## Implementation Steps
1. [ ] Step 1 - [description]
   - Files: `path/to/file.ts`
   - Verify: [how to verify]
   
2. [ ] Step 2 - [description]
   - Files: `path/to/file.ts`
   - Verify: [how to verify]

## Risks
- [Potential issue and mitigation]

## Next Action
Review this plan. Then `/clear` and say "execute step 1"
```

## Rules
- Planning only, no code execution
- Break into smallest possible steps
- Each step should be independently executable
- Define verification criteria for each step
- Use `/clear` after planning to save context
