# /security - Security Audit

## Usage
```
/security [target]
```

### Targets
- File: `/security src/auth.ts`
- Directory: `/security src/`
- Full project: `/security`

## Purpose
Scan for security vulnerabilities and suggest fixes.

## Checks

### 🔴 Critical
- SQL/NoSQL injection
- Command injection
- Path traversal
- Hardcoded secrets/credentials
- Unsafe deserialization

### 🟠 High
- XSS vulnerabilities
- CSRF missing
- Insecure dependencies
- Weak cryptography
- Missing authentication

### 🟡 Medium
- Information disclosure
- Missing rate limiting
- Verbose error messages
- Insecure cookies

## Output Format
```markdown
## Security Audit: [target]

### 🔴 Critical (N)
- `auth.ts:45` - SQL injection
  → Use parameterized queries
  
### 🟠 High (N)
- `api.ts:12` - Missing auth check
  → Add middleware

### 🟡 Medium (N)
- `error.ts:8` - Stack trace exposed
  → Hide in production

### Dependencies
- lodash@4.17.15 - Prototype pollution
  → Upgrade to 4.17.21

### Score: 7/10
```

## Auto-Fix
Safe fixes applied automatically:
- Update vulnerable deps
- Add missing headers
- Sanitize obvious inputs
