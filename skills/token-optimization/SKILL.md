---
name: token-optimization
description: Strategies to minimize token usage while maintaining effectiveness
---

# Token Optimization

## Why It Matters
Claude's context window fills up fast. Performance degrades as it fills. Managing context is critical.

## Principles

### 1. Read Minimally
- Read specific sections, not entire files
- Use `read --offset --limit` for large files
- Don't re-read files you've already seen
- Let Claude fetch what it needs on demand

### 2. Output Minimally  
- Summaries over full explanations
- Show only changed code, not entire files
- Skip repetitive content
- No unnecessary confirmations

### 3. Manage Context
- `/clear` after completing tasks
- One session = one focused task
- Don't mix unrelated conversations
- Use subagents for large explorations

### 4. Efficient Tool Use
- Batch multiple file edits together
- Run independent operations in parallel
- Avoid redundant verification questions
- Trust verification commands (tests, lint)

## Anti-Patterns
❌ Reading entire file to change one line
❌ Repeating the same explanation
❌ Re-confirming known information
❌ Long greetings/closings in every message
❌ Asking "should I proceed?" when the task is clear

## Context Window Tips
- Track usage with status line
- Compact when context > 70% full
- Start fresh session for new tasks
- Use CLAUDE.md for persistent context (loaded every session)
