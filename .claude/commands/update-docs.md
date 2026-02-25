# /update-docs - Sync Documentation with Code

## Usage
```
/update-docs [target]
```

### Targets
- All docs: `/update-docs`
- Specific: `/update-docs README.md`
- API docs: `/update-docs api`

## Purpose
Automatically update documentation to match current code state.
Finds outdated docs and brings them in sync.

## Flow

```
┌─────────────────────────────────────────────────────┐
│  /update-docs                                       │
├─────────────────────────────────────────────────────┤
│  1. COMPARE    │ Code vs documentation              │
│  2. IDENTIFY   │ Find mismatches                    │
│  3. UPDATE     │ Fix outdated sections              │
│  4. VERIFY     │ Ensure accuracy                    │
│  5. REPORT     │ Summary of changes                 │
└─────────────────────────────────────────────────────┘
```

## What It Updates

### README.md
- Installation instructions
- Usage examples
- Feature lists
- API references

### API Documentation
- Endpoint descriptions
- Request/response schemas
- Parameter documentation

### Code Comments
- JSDoc/docstrings
- Function signatures
- Type definitions

## Output
```markdown
## Documentation Updated

### Changed Files
- README.md: Updated installation section
- docs/api.md: Added new endpoint /users

### Verified
✅ Examples still work
✅ Links valid
✅ Code samples accurate
```

## Token Optimization
- Only reads files that need checking
- Updates incrementally
- Skips unchanged sections
