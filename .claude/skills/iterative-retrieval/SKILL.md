# Iterative Retrieval Skill

Progressive context refinement for complex codebases.

## When to Use
- Large codebases where full context doesn't fit
- Finding relevant code across many files
- Understanding complex dependencies

## Process

### Phase 1: Broad Search
```
1. Start with high-level search (file names, directory structure)
2. Identify candidate areas (3-5 most relevant)
3. Note confidence level for each
```

### Phase 2: Targeted Drill-Down
```
1. Read headers/exports of candidate files
2. Identify key functions/classes
3. Narrow to 1-2 most relevant files
```

### Phase 3: Deep Context
```
1. Read full implementation of target code
2. Trace dependencies (imports, calls)
3. Build complete mental model
```

## Output Format
After each phase, summarize:
- What was found
- Confidence level (low/medium/high)
- Next retrieval action needed

## Benefits
- Reduces token usage by ~60%
- Avoids context window overflow
- More accurate results than single broad search
