# Architecture Decision Record (ADR)

Create or update Architecture Decision Records for this project.

## Arguments

- `$ARGUMENTS` - Decision title or topic (e.g., "Use PostgreSQL for primary database")

## Tasks

1. **If creating new ADR:**
   - Create `docs/adr/` directory if it doesn't exist
   - Number sequentially (e.g., `0001-use-postgresql.md`)
   - Use standard ADR template

2. **ADR Template:**
   ```markdown
   # ADR-XXXX: [Title]

   ## Status
   [Proposed | Accepted | Deprecated | Superseded]

   ## Context
   What is the issue that we're seeing that is motivating this decision?

   ## Decision
   What is the change that we're proposing and/or doing?

   ## Consequences
   What becomes easier or harder as a result of this decision?

   ## Alternatives Considered
   What other options were evaluated?
   ```

3. **If reviewing existing ADRs:**
   - List all ADRs with status
   - Identify any that may need updates
   - Check for conflicting decisions

## Output

Create/update the ADR file and provide a summary of the decision documented.
