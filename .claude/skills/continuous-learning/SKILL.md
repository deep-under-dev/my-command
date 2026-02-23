# Continuous Learning Skill

Learn from mistakes and successes during development sessions.

## When to Use
- After debugging sessions
- When discovering new patterns
- After solving complex problems

## Process

### 1. Capture Learning
When something notable happens:
```
Pattern: [what worked/failed]
Context: [when this applies]
Confidence: [high/medium/low]
```

### 2. Apply Learnings
Before similar tasks, recall relevant learnings:
- Check for matching patterns
- Apply high-confidence solutions first
- Update confidence based on results

### 3. Refine Over Time
- Promote successful patterns (increase confidence)
- Demote or remove failed patterns
- Merge similar learnings

## Example Instinct Format
```yaml
---
pattern: "async/await error handling"
context: "Node.js API endpoints"
confidence: high
learned: "2026-02-01"
---
Always wrap async handlers with try-catch.
Return consistent error responses with status codes.
```

## Integration
- Store learnings in `.claude/instincts/`
- Load relevant instincts at session start
- Update after significant debugging sessions
