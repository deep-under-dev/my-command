# Loop Status

Check the status of an active continuous agent loop.

## Usage

```
/loop-status
```

## Output

- **Loop State**: running | paused | stopped
- **Current Step**: Step number and description
- **Progress**: Completed vs remaining tasks
- **Quality Gates**: Pass/fail status
- **Runtime**: Duration since loop start
- **Errors**: Any encountered issues

## Related

- `/loop-start` - Start a new loop
- `/quality-gate` - Run quality checks
