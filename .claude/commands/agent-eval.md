# Agent Evaluation

Compare coding agents head-to-head on the same task.

## Usage

```
/agent-eval <task_description>
```

## Process

1. **Define Task**: Clear, measurable coding task
2. **Setup Harness**: Create isolated test environments
3. **Run Agents**: Execute same task across agents (Claude Code, Cursor, Codex, etc.)
4. **Collect Metrics**:
   - Completion time
   - Token usage
   - Code quality (lint, types, tests)
   - Iteration count
5. **Compare Results**: Side-by-side analysis

## Metrics Template

| Agent | Time | Tokens | Quality | Iterations | Notes |
|-------|------|--------|---------|------------|-------|
| Agent A | - | - | - | - | - |
| Agent B | - | - | - | - | - |

## Output

- Comparison table
- Winner recommendation
- Detailed analysis per agent

## Example

```
/agent-eval "Implement a REST API endpoint for user authentication with JWT"
```
