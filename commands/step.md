# /step - Execute Single Step

## Usage
```
/step [step_number]
```

## Purpose
Execute one step from a previous `/plan` or `/build` output. Keeps context clean by focusing on one thing at a time.

## Flow
1. Execute the specified step only
2. Write tests first (TDD approach)
3. Implement the change
4. Verify (run tests, lint, typecheck)
5. Report completion

## Output Format
```markdown
## Step [N]: [Title]

### Changes Made
- `path/to/file.ts` - [what changed]

### Verification
✅ Tests pass
✅ Lint pass
✅ Types check

### Next
Run `/clear` then `/step [N+1]`
```

## Rules
- One step at a time
- Must verify before marking complete
- Use `/clear` between steps to save context
- If step fails, fix before proceeding
