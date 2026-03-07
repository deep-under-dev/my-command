# Quality Gate

Run comprehensive quality checks before merge/deploy.

## Checklist

1. **Tests**: All tests pass
2. **Types**: No type errors
3. **Lint**: No linting issues
4. **Security**: No known vulnerabilities
5. **Coverage**: Meets threshold (if configured)
6. **Build**: Clean build succeeds

## Usage

```
/quality-gate           # Check current directory
/quality-gate --strict  # Fail on warnings too
```

## Auto-Detection

Runs appropriate checks based on project:
- `package.json` → npm test, tsc, eslint
- `pyproject.toml` → pytest, mypy, ruff
- `go.mod` → go test, go vet
- `Cargo.toml` → cargo test, cargo clippy

## Output

- ✅ Pass: Ready to merge
- ⚠️ Warn: Review before merge
- ❌ Fail: Fix required
