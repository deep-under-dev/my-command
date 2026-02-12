# /auto - Automated Feature Development

## Usage
```
/auto "feature description"
```

## Purpose
Single command that handles the entire development cycle automatically:
**Build → Verify → Fix → Test → Complete**

No manual intervention needed. Context is managed automatically.

## Automated Flow

```
┌─────────────────────────────────────────────────────┐
│  /auto "feature"                                    │
├─────────────────────────────────────────────────────┤
│  1. EXPLORE    │ Read relevant files, find patterns │
│  2. PLAN       │ Break into steps, set criteria     │
│  3. IMPLEMENT  │ Code each step with TDD            │
│  4. VERIFY     │ Run tests, lint, typecheck         │
│  5. FIX        │ Auto-fix any failures              │
│  6. COMPLETE   │ Summary + commit suggestion        │
└─────────────────────────────────────────────────────┘
```

## Internal Process

### Phase 1: Explore (Token-efficient)
- Read ONLY relevant files (not entire codebase)
- Identify patterns from similar features
- Map dependencies

### Phase 2: Plan (Minimal output)
- Break into 2-5 small steps
- Each step has clear verification
- No verbose explanations

### Phase 3: Implement Loop
For each step:
```
write test → implement → run test → pass? → next step
                              ↓ fail
                         auto-fix → retry (max 3)
```

### Phase 4: Verify All
```bash
npm test        # or project's test command
npm run lint    # auto-fix if possible
npm run typecheck
npm run build
```

### Phase 5: Auto-Fix
- If tests fail → analyze error → fix → retry
- If lint fails → run auto-fix
- If types fail → fix type errors
- Max 3 retry attempts per issue

### Phase 6: Complete
```markdown
## ✅ Complete: [feature]

### Changes
- `path/file.ts` - [what changed]

### Verification
✅ Tests: 12 passed
✅ Lint: clean
✅ Types: no errors

### Commit
git commit -m "feat: [description]"
```

## Token Optimization
- No progress updates between steps
- No "should I continue?" questions
- Errors only shown if auto-fix fails
- Final summary only

## Rules
- Never ask for confirmation mid-process
- Auto-fix before reporting errors
- Stop only on unrecoverable failures
- Always end with verification summary
