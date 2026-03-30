# Architecture Decision Records (ADR) Skill

## Purpose
Capture and manage architectural decisions in a structured, searchable format.

## ADR Template

```markdown
# ADR-{NUMBER}: {TITLE}

## Status
{Proposed | Accepted | Deprecated | Superseded by ADR-XXX}

## Context
What is the issue that we're seeing that is motivating this decision?

## Decision
What is the change that we're proposing and/or doing?

## Consequences
What becomes easier or harder because of this change?

## Alternatives Considered
- Option A: ...
- Option B: ...
```

## Workflow

1. **Create**: `mkdir -p docs/adr && touch docs/adr/0001-record-architecture-decisions.md`
2. **Number**: Use sequential 4-digit numbers (0001, 0002, ...)
3. **Index**: Maintain `docs/adr/README.md` with links to all ADRs
4. **Review**: ADRs should be reviewed in PRs like code

## Commands

```bash
# List all ADRs
ls docs/adr/*.md

# Search ADRs
grep -r "keyword" docs/adr/

# Create new ADR
NEXT=$(ls docs/adr/*.md 2>/dev/null | wc -l | xargs -I {} expr {} + 1)
printf -v NUM "%04d" $NEXT
touch "docs/adr/${NUM}-title.md"
```

## Best Practices

- Keep ADRs immutable once accepted (supersede instead of edit)
- Link related ADRs
- Include date in status changes
- Store close to the code they affect
