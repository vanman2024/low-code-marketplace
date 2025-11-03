# Low Code Marketplace - Claude Code Configuration

## 🚨 CRITICAL: Security Rules - NO HARDCODED API KEYS

**This is the HIGHEST PRIORITY security rule for ALL plugins in this marketplace.**

### Absolute Prohibition

❌ **NEVER EVER** hardcode API keys, secrets, or credentials in:
- Agent prompts
- Command prompts
- Skill documentation
- Generated code
- Low-code configurations
- Templates or examples

### Required Practice

✅ **ALWAYS use placeholders:**
```bash
ANTHROPIC_API_KEY=your_anthropic_key_here
AIRTABLE_API_KEY=your_airtable_key_here
ZAPIER_API_KEY=your_zapier_key_here
```

✅ **ALWAYS read from environment:**
```python
import os
api_key = os.getenv("ANTHROPIC_API_KEY")
```

### Comprehensive Security Guidelines

See `@docs/security/SECURITY-RULES.md` for full validation checklist and comprehensive security guidelines.

**Before ANY commit to this marketplace:**
- [ ] No real API keys in any file
- [ ] All examples use obvious placeholders
- [ ] `.gitignore` protects secrets
- [ ] Generated code enforces security

**Violations = Immediate fix required before merge**

---

## Low Code Marketplace Purpose

This marketplace contains plugins for low-code/no-code integrations and automation platforms.

### Plugin Structure

All low-code plugins follow Claude Code's plugin system conventions.

### Component Types

- **Agents**: Specialized for low-code platform integration
- **Commands**: User-facing commands for automation workflows
- **Skills**: Reusable patterns for common low-code scenarios

### Reference

For plugin-specific documentation, see individual plugin README files.
