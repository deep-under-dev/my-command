# /deep-review - Comprehensive Code Review

## Usage
```
/deep-review [target]
```

### Targets
- File: `/deep-review src/auth.ts`
- Directory: `/deep-review src/services/`
- PR: `/deep-review #123`
- Focused: `/deep-review src/ --security`

## Checklist

### Security
- [ ] Injection vulnerabilities (SQL, XSS, command)
- [ ] Authentication/authorization flaws
- [ ] Hardcoded secrets or credentials
- [ ] Insecure data handling
- [ ] Input validation

### Quality
- [ ] Potential bugs
- [ ] Edge case handling
- [ ] Error handling
- [ ] Code duplication
- [ ] Dead code

### Performance
- [ ] N+1 queries
- [ ] Unnecessary computations
- [ ] Memory leaks
- [ ] Blocking operations

### Maintainability
- [ ] Code readability
- [ ] Test coverage
- [ ] Documentation
- [ ] Naming conventions

## Output Format
```markdown
## Review: [target]

### Summary
- Severity: 🔴 High / 🟡 Medium / 🟢 Low
- Issues found: N

### 🔴 Critical (Fix Immediately)
#### 1. [Issue Title]
- File: `path/to/file.ts:123`
- Problem: ...
- Solution: ...

### 🟡 Should Fix
...

### 🟢 Suggestions
...

### Strengths
- What's done well
```

## Token Optimization
- Review changed files only, not entire codebase
- Use `--security` or `--performance` for focused reviews
- For large PRs, review file by file
