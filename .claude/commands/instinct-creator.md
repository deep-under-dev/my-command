# /instinct-creator - Create Instincts from Repository Patterns

## Usage
```
/instinct-creator [scope]
```

### Scopes
- `all` - Analyze entire repository
- `recent` - Last 50 commits only
- `path/to/dir` - Specific directory

## Purpose
Automatically discover and codify implicit patterns in your codebase into explicit instincts that Claude Code follows.

## What Are Instincts?
Instincts are behavioral rules derived from your actual code patterns:
- Naming conventions you follow
- Error handling patterns you prefer
- Import ordering styles
- Testing patterns unique to your project

## Process Flow

```
┌─────────────────────────────────────────────────────┐
│  /instinct-creator                                  │
├─────────────────────────────────────────────────────┤
│  1. SCAN       │ Analyze code structure & history   │
│  2. DETECT     │ Find recurring patterns            │
│  3. EXTRACT    │ Codify into instinct rules         │
│  4. VALIDATE   │ Check against existing code        │
│  5. GENERATE   │ Create .claude/instincts/*.md      │
└─────────────────────────────────────────────────────┘
```

## Output
Creates instinct files in `.claude/instincts/`:
```
.claude/instincts/
├── naming.md        # Variable/function naming patterns
├── error-handling.md # How errors are caught/thrown
├── testing.md       # Test structure preferences
└── imports.md       # Import organization style
```

## Example Instinct
```markdown
# Instinct: Error Handling

## Pattern
All async functions use try-catch with specific error types.

## Rule
When writing async code:
1. Wrap in try-catch
2. Catch specific error types first
3. Re-throw with context: `throw new AppError('context', { cause: err })`
```

## Token Optimization
- Samples representative files only
- Skips generated/vendor code
- Outputs minimal, actionable rules
