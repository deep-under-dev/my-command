# /review - Quick Code Review

## Usage
```
/review [file_path or PR_number]
```

## Purpose
Fast, lightweight code review. Use `/deep-review` for comprehensive analysis.

## Checklist
- [ ] Obvious bugs
- [ ] Security red flags
- [ ] Code style issues
- [ ] Missing error handling
- [ ] Test coverage

## Output Format
```markdown
## Review: [target]

### Summary
[One paragraph assessment]

### Issues
- 🔴 [Critical issues]
- 🟡 [Improvements needed]
- 🟢 [Suggestions]

### Verdict
✅ Approve / ❌ Request Changes
```

## When to Use
- Quick PR reviews
- Sanity check before commit
- Spot check specific files

For thorough analysis, use `/deep-review` instead.
