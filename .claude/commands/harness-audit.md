# Harness Audit

Baseline reliability and risk assessment for agent harness configuration.

## Usage

```
/harness-audit [path]
```

## Steps

1. **Configuration Check**
   - Verify hook settings (ECC_HOOK_PROFILE, ECC_DISABLED_HOOKS)
   - Check cross-platform compatibility
   - Validate skill loading

2. **Risk Assessment**
   - Identify fragile hook patterns
   - Check for non-interactive environment issues
   - Review path handling (especially Windows)

3. **Recommendations**
   - Suggest hook profile: minimal|standard|strict
   - List hooks to disable if problematic
   - Propose fixes for identified issues

## Output

- Summary of current harness state
- Risk score (low/medium/high)
- Actionable recommendations
