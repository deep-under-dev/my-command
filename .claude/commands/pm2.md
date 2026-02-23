# PM2 Multi-Agent Orchestration

Manage multiple Claude Code agents using PM2 process manager.

## Setup
```bash
npm install -g pm2
```

## Commands

### Start Agent Pool
```bash
pm2 start ecosystem.config.js
```

### Monitor Agents
```bash
pm2 monit
pm2 logs
```

### Scale Agents
```bash
pm2 scale agent-worker 4
```

## Example ecosystem.config.js
```javascript
module.exports = {
  apps: [
    {
      name: 'agent-main',
      script: 'claude',
      args: '--resume',
      cwd: '/path/to/project',
      instances: 1
    },
    {
      name: 'agent-worker',
      script: 'claude',
      args: '--task "background analysis"',
      cwd: '/path/to/project',
      instances: 2
    }
  ]
};
```

## Orchestration Patterns

### Parallel Task Distribution
1. Main agent receives complex task
2. Spawns worker agents via PM2
3. Each worker handles subtask
4. Main agent aggregates results

### Session Handoff
1. Agent completes phase
2. Saves context to shared file
3. Next agent picks up with `--resume`

## Best Practices
- Use unique session IDs per agent
- Share context via files, not memory
- Set resource limits per agent
- Monitor with `pm2 monit`
