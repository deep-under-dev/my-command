# My Commands

A collection of Claude Code commands and skills optimized for efficient development workflows.

## Structure

```
my-command/
├── .claude/
│   ├── commands/              # Slash commands
│   │   ├── auto.md            # /auto - Full automated workflow
│   │   ├── auto-review.md     # /auto-review - Review + auto-fix
│   │   ├── build.md           # /build - Feature implementation
│   │   ├── deep-review.md     # /deep-review - Comprehensive review
│   │   ├── overview.md        # /overview - Project analysis
│   │   ├── plan.md            # /plan - Implementation planning
│   │   ├── review.md          # /review - Quick review
│   │   └── step.md            # /step - Step execution
│   ├── rules/
│   │   └── workflow.md        # Workflow rules
│   ├── skills/
│   │   ├── auto-context/      # Auto context management
│   │   ├── exploration/       # Explore before coding
│   │   ├── token-optimization/# Minimize token usage
│   │   └── verification/      # Self-verification loops
│   └── settings.local.json
├── CLAUDE.md
└── README.md
```

## Quick Start

### Automated Workflow (Recommended)
```
/auto "add feature X"    # Full cycle: Build → Verify → Fix → Test → Complete
```

### Manual Workflow
```
/overview              # Understand the project
/plan "add feature X"  # Plan implementation
/clear                 # Clean context
/step 1                # Execute step 1
...
```

### Code Review
```
/auto-review src/             # Review + auto-fix
/review src/file.ts           # Quick review
/deep-review src/ --security  # Comprehensive review
```

## Installation

Copy `.claude/` folder to your project root:

```bash
git clone https://github.com/deep-under-dev/my-command.git
cp -r my-command/.claude /path/to/your/project/
```

Or link globally:
```bash
cp -r my-command/.claude ~/.claude/
```

## Key Principles

1. **Automate everything** - Use `/auto` for hands-free development
2. **Verify your work** - Tests, lint, and type checks
3. **Manage context** - Auto-context handles this for you
4. **Token efficiency** - Minimal reads, no verbose output

## References

- [Claude Code Best Practices](https://code.claude.com/docs/en/best-practices)
- [everything-claude-code](https://github.com/affaan-m/everything-claude-code)
