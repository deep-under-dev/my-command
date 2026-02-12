---
name: auto-context
description: Automatic context management for token efficiency
---

# Auto Context Management

## Purpose
Automatically manage context window to maximize efficiency and accuracy.

## Principles

### 1. Lazy Loading
- Don't read files until needed
- Read specific sections, not entire files
- Cache file summaries in memory

### 2. Progressive Refinement
```
Start: Minimal context (task + key files)
  ↓
Add: Only what's needed for current step
  ↓
Prune: Remove completed step details
  ↓
End: Only keep results
```

### 3. Smart Compaction
When context > 60% full:
- Summarize completed work
- Remove intermediate outputs
- Keep only: task, current state, next steps

### 4. Subagent Delegation
For large explorations:
- Spawn subagent with focused context
- Receive summary back
- Main context stays clean

## Implementation

### Before Each Step
```
Check: Is this information already in context?
  YES → Use existing
  NO  → Fetch minimal needed
```

### After Each Step
```
Keep: Results, errors, next action
Drop: Intermediate output, verbose logs
```

### On Error
```
Keep: Error message, relevant code
Drop: Successful steps (summarize only)
```

## Anti-Patterns
❌ Loading entire codebase at start
❌ Keeping all file contents in context
❌ Verbose progress updates
❌ Repeating task description in each step
❌ Asking confirmation questions
