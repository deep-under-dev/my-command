# /auto-review - Automated Code Review & Fix

## Usage
```
/auto-review [target]
```

### Targets
- File: `/auto-review src/auth.ts`
- Directory: `/auto-review src/`
- PR: `/auto-review #123`

## Purpose
Review code AND automatically fix issues found.
No back-and-forth - just results.

## Automated Flow

```
┌─────────────────────────────────────────────────────┐
│  /auto-review src/                                  │
├─────────────────────────────────────────────────────┤
│  1. SCAN      │ Find issues (security, bugs, style) │
│  2. CLASSIFY  │ Critical vs fixable vs suggestions  │
│  3. AUTO-FIX  │ Fix everything that's safe to fix   │
│  4. VERIFY    │ Run tests after fixes               │
│  5. REPORT    │ Summary of changes + remaining      │
└─────────────────────────────────────────────────────┘
```

## Auto-Fix Categories

### ✅ Will Auto-Fix
- Lint errors (via eslint --fix)
- Formatting issues
- Simple type errors
- Missing error handling (add try-catch)
- Unused imports/variables

### ⚠️ Will Report (Not Auto-Fix)
- Security vulnerabilities (need human review)
- Logic bugs (need understanding)
- Architecture issues
- Breaking changes

## Output Format
```markdown
## Review Complete: [target]

### 🔧 Auto-Fixed (N issues)
- `file.ts:23` - Added missing null check
- `file.ts:45` - Fixed unused import

### ⚠️ Needs Attention (N issues)
- `auth.ts:12` - 🔴 SQL injection risk
  → Recommendation: Use parameterized query

### Verification
✅ Tests pass after fixes
✅ Lint clean

### Commit
git commit -m "fix: Auto-fix from code review"
```

## Token Optimization
- Scan without verbose output
- Fix silently
- Report only final state
- No intermediate updates
