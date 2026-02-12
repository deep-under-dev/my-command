# My Commands

A collection of Claude Code commands and skills optimized for efficient development workflows.

## Structure

```
my-command/
├── commands/              # Slash commands
│   ├── build.md           # /build - Full feature implementation
│   ├── overview.md        # /overview - Project analysis
│   ├── deep-review.md     # /deep-review - Comprehensive code review
│   ├── plan.md            # /plan - Implementation planning
│   ├── step.md            # /step - Step-by-step execution
│   └── review.md          # /review - Quick code review
├── skills/                # Knowledge and workflows
│   ├── token-optimization/    # Minimize token usage
│   ├── verification/          # Self-verification loops
│   └── exploration/           # Explore before coding
├── rules/                 # Always-follow guidelines
│   └── workflow.md        # Standard workflow rules
├── agents/                # Subagents (coming soon)
└── .claude/               # Claude configuration
```

## Quick Start

### Basic Workflow
```
/overview              # Understand the project
/plan "add feature X"  # Plan implementation
/clear                 # Clean context
/step 1                # Execute step 1
/clear                 # Clean context
/step 2                # Execute step 2
...
```

### Code Review
```
/review src/file.ts           # Quick review
/deep-review src/             # Comprehensive review
/deep-review src/ --security  # Security focused
```

## Installation

Copy to your Claude Code configuration:

```bash
# Commands
cp -r commands/* ~/.claude/commands/

# Skills
cp -r skills/* ~/.claude/skills/

# Rules
cp -r rules/* ~/.claude/rules/
```

## Key Principles

1. **Plan before code** - Always understand before implementing
2. **Verify your work** - Use tests, lint, and type checks
3. **Manage context** - Use `/clear` between tasks
4. **Token efficiency** - Read/write only what's needed

## References

- [Claude Code Best Practices](https://code.claude.com/docs/en/best-practices)
- [everything-claude-code](https://github.com/affaan-m/everything-claude-code)
