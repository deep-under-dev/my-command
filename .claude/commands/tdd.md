# /tdd - Test-Driven Development Flow

## Usage
```
/tdd "feature description"
```

## Purpose
Strict TDD workflow: Red → Green → Refactor

## Flow

```
┌─────────────────────────────────────────────────────┐
│  /tdd "add user validation"                         │
├─────────────────────────────────────────────────────┤
│  1. RED       │ Write failing test first            │
│  2. GREEN     │ Minimal code to pass                │
│  3. REFACTOR  │ Clean up, keep tests green          │
│  4. REPEAT    │ Next test case                      │
└─────────────────────────────────────────────────────┘
```

## TDD Rules
- **Never** write production code without a failing test
- **Minimal** implementation - just enough to pass
- **Refactor** only when tests are green
- **Small** increments - one test at a time

## Output Format
```markdown
## TDD: [feature]

### 🔴 RED - Test Written
`test/user.test.ts`
- it('should reject empty email')

### 🟢 GREEN - Passing
`src/user.ts` - Added validation

### 🔄 REFACTOR
- Extracted validateEmail helper
- Tests still pass ✅

### Coverage
+2 tests | 94% coverage
```

## Integration
Works with: Jest, Vitest, Mocha, pytest, go test
