# /loop-start - Start Continuous Agent Loop

Begin an autonomous development loop for iterative task completion.

## Usage
```
/loop-start [task-description] --max-iterations=[N] --checkpoint=[interval]
```

## Parameters
- `task-description`: What to accomplish
- `--max-iterations`: Maximum loop cycles (default: 10)
- `--checkpoint`: Save progress every N iterations (default: 3)

## Loop Behavior

### Each Iteration
1. **Assess**: Check current state vs. goal
2. **Plan**: Decide next smallest step
3. **Execute**: Implement the step
4. **Verify**: Test/validate the change
5. **Log**: Record progress

### Exit Conditions
- Task completed successfully
- Max iterations reached
- Blocking error encountered
- User interruption

## Safety
- Creates checkpoint commits at intervals
- Logs all actions for review
- Pauses on destructive operations
- Can be stopped with `/loop-stop`

## Best For
- Multi-step refactoring
- Test coverage expansion
- Documentation generation
- Migration tasks
