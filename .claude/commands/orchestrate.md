# Multi-Agent Orchestration

Coordinate multiple specialized agents to tackle complex tasks efficiently.

## Usage
When facing a complex task that spans multiple domains (e.g., full-stack feature):

1. **Decompose** the task into independent subtasks
2. **Assign** each subtask to a specialized agent:
   - `architect` - System design, API contracts
   - `backend` - Server logic, database
   - `frontend` - UI components, state
   - `tester` - Test coverage, E2E
   - `security` - Vulnerability audit
   - `reviewer` - Code quality check

3. **Coordinate** results and resolve conflicts
4. **Integrate** all pieces together

## Workflow
```
[Main Agent] ─┬─> [Architect] ─> design.md
              ├─> [Backend]   ─> api/
              ├─> [Frontend]  ─> ui/
              └─> [Tester]    ─> tests/
                      ↓
              [Integration & Review]
```

## Best Practices
- Each agent works in isolation with clear inputs/outputs
- Use shared context files for cross-agent communication
- Run independent tasks in parallel when possible
- Always have a final integration/review step
