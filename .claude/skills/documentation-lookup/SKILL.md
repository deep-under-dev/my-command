# Documentation Lookup Skill

Efficient documentation retrieval patterns for coding agents.

## Purpose
Enable fast, accurate documentation lookups without hallucinating APIs.

## Patterns

### 1. Official Docs First
- Always prefer official documentation sources
- Use versioned docs matching project dependencies
- Verify API signatures before suggesting

### 2. Search Strategies
- Framework docs: Check official site first
- Language stdlib: Use language reference
- Libraries: README → docs/ → source code

### 3. Caching
- Remember frequently accessed docs
- Note version-specific differences
- Track deprecated APIs

### 4. Verification
- Cross-reference multiple sources when uncertain
- Check changelogs for recent API changes
- Test code snippets when possible

## Anti-Patterns
- Don't guess API signatures
- Don't assume methods exist without checking
- Don't mix documentation from different versions
