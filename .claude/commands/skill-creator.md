# /skill-creator - AI-Powered Skill Generation

## Usage
```
/skill-creator [target]
```

### Targets
- Directory: `/skill-creator src/`
- Repository: `/skill-creator .`
- Pattern: `/skill-creator "database migrations"`

## Purpose
Analyze repository patterns and automatically generate reusable SKILL.md files.

## Flow

```
┌─────────────────────────────────────────────────────┐
│  /skill-creator src/                                │
├─────────────────────────────────────────────────────┤
│  1. ANALYZE   │ Scan commits, files, patterns       │
│  2. IDENTIFY  │ Find repeating workflows            │
│  3. EXTRACT   │ Document the pattern                │
│  4. GENERATE  │ Create SKILL.md with steps          │
│  5. VALIDATE  │ Ensure skill is actionable          │
└─────────────────────────────────────────────────────┘
```

## Pattern Detection
- Multi-file changes that occur together
- Repeated commit sequences
- Common file creation patterns
- Testing + implementation pairs

## Output
Creates `.claude/skills/{skill-name}/SKILL.md` with:
- Clear trigger conditions
- Step-by-step instructions
- File templates if applicable
- Verification criteria

## Example
```
/skill-creator "API endpoints"

→ Generates: .claude/skills/api-endpoint/SKILL.md
  - Route file creation
  - Validation setup
  - Test scaffolding
  - Documentation update
```
