# /hook-creator - Generate Hooks from Conversation Analysis

## Usage
```
/hook-creator [type]
```

### Types
- `all` - Generate all hook types
- `pre` - PreToolUse hooks only
- `post` - PostToolUse hooks only
- `session` - Session lifecycle hooks

## Purpose
Analyze your Claude Code conversations to discover automation opportunities and generate hooks that automate repetitive workflows.

## What Are Hooks?
Hooks intercept Claude Code tool calls and can:
- Block dangerous operations
- Auto-run tests after file changes
- Enforce code standards before commits
- Log actions for audit trails

## Process Flow

```
┌─────────────────────────────────────────────────────┐
│  /hook-creator                                      │
├─────────────────────────────────────────────────────┤
│  1. ANALYZE    │ Review conversation history        │
│  2. IDENTIFY   │ Find repetitive manual steps       │
│  3. MATCH      │ Map to hook event types            │
│  4. GENERATE   │ Create hook implementations        │
│  5. TEST       │ Validate hooks work correctly      │
└─────────────────────────────────────────────────────┘
```

## Hook Types

### PreToolUse
Runs BEFORE a tool executes:
```javascript
// Block rm -rf on protected paths
{
  event: "PreToolUse",
  tool: "Bash",
  match: /rm\s+-rf/,
  action: "block",
  message: "Destructive command blocked"
}
```

### PostToolUse
Runs AFTER a tool completes:
```javascript
// Auto-run tests after file edit
{
  event: "PostToolUse", 
  tool: "Write",
  match: /\.test\.(ts|js)$/,
  action: "run",
  command: "npm test"
}
```

### SessionStart/End
Runs at session boundaries:
```javascript
// Log session start
{
  event: "SessionStart",
  action: "log",
  message: "Session started: ${timestamp}"
}
```

## Output
Creates hooks in `.claude/hooks/`:
```
.claude/hooks/
├── security.js      # Block dangerous commands
├── auto-test.js     # Run tests on changes
├── lint-check.js    # Lint before commits
└── audit-log.js     # Log all actions
```

## Token Optimization
- Focuses on high-frequency patterns
- Generates minimal viable hooks
- Skips one-off workflows
