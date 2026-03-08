# /model-route - Intelligent Model Routing

Route tasks to the optimal model based on complexity, cost, and capability requirements.

## Usage
```
/model-route [task-description]
```

## Routing Logic

### Quick Tasks (Fast Model)
- Simple questions, lookups
- Code formatting, linting fixes
- Basic file operations
- Typo corrections

### Standard Tasks (Default Model)
- Feature implementation
- Bug fixes
- Code review
- Documentation

### Complex Tasks (Thinking Model)
- Architecture decisions
- Complex debugging
- Multi-file refactoring
- System design
- Security analysis

## Decision Factors
1. **Complexity**: Lines of code, number of files, interdependencies
2. **Risk**: Production impact, security sensitivity
3. **Novelty**: Standard patterns vs. novel solutions needed
4. **Context**: Amount of codebase knowledge required

## Output
Recommend the appropriate model tier and explain reasoning briefly.
