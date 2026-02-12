# /build - Feature Implementation

## Usage
```
/build "feature description"
```

## Flow (Based on Claude Code Best Practices)

### 1. Explore
- Read relevant files
- Understand existing patterns
- Check dependencies

### 2. Plan
- Break into small steps
- Define file changes
- Set verification criteria

### 3. Confirm
- Present plan to user
- Wait for approval
- Adjust if needed

### 4. Implement
- One step at a time
- Write tests first (TDD)
- Verify after each step

### 5. Verify
- Run tests
- Run linter
- Check types

## Output Format
```markdown
## Feature: [name]

### Exploration
- Related files: ...
- Existing patterns: ...

### Implementation Plan
1. [ ] Step 1 - description
2. [ ] Step 2 - description

### Verification
- Tests: `npm test path/to/test`
- Success criteria: ...

### Next Action
After reviewing, run `/clear` then say "proceed with step 1"
```

## Rules
- Never code before planning
- Each step must be independently verifiable
- Always define success criteria upfront
- Use `/clear` between major steps
