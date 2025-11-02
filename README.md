# Low-Code Marketplace

**Quick system integrations and workflow automation without building full applications**

## Overview

The **low-code-marketplace** provides programmatic control over automation platforms (N8N, Make.com, Zapier) through MCP servers and APIs. Connect existing systems in minutes instead of days - no UI required, everything built from Claude Code.

## Purpose

### When to Use This Marketplace

**Use low-code-marketplace when:**
- Connecting existing systems quickly (e.g., Cats One ATS → Google Sheets)
- Building workflow automations without custom code
- Quick integrations between 2-3 systems
- AI-enhanced data pipelines
- Event-driven automations

**Example Use Cases:**
- Cats One (ATS) → Google Sheets sync
- Email automation with AI responses
- Multi-system sync (Notion + Slack + Sheets)
- AI data enrichment workflows
- Webhook processing pipelines

### When NOT to Use This Marketplace

**Use ai-tech-stack-marketplace instead when:**
- Building complete applications from scratch
- Need custom UI and complex backend logic
- Building SaaS products
- Full control over everything

## Architecture

```
Marketplaces Ecosystem:
├── dev-lifecycle-marketplace/    # Universal foundation
├── ai-tech-stack-marketplace/    # Build NEW AI applications
└── low-code-marketplace/         # Connect EXISTING systems (this one!)
```

### Integration with Other Marketplaces

Low-code plugins can reference ai-tech-stack plugins:

```bash
# Deploy custom ML model (ai-tech-stack)
/ml-training:deploy-inference
# Returns: https://modal-app.modal.run/classify

# Create workflow to use it (low-code)
/n8n:create-workflow ai-pipeline
/n8n:add-node http-request url=https://modal-app.modal.run/classify
```

## Plugins

### Planned Plugins

1. **n8n** (Priority 1) - Self-hosted workflow automation
   - Full programmatic control via API
   - 400+ integrations
   - Perfect for AI workflows
   - Free (self-hosted)

2. **zapier** (Priority 2) - Cloud automation platform
   - 5000+ app integrations
   - Good API support
   - Enterprise-grade reliability
   - Paid service

3. **make** (Priority 3) - Visual workflow automation
   - 1500+ integrations
   - Budget-friendly pricing
   - Limited API (template-based)
   - Cloud service

4. **integration-orchestrator** - High-level workflow patterns
   - Common integration patterns
   - Cross-platform workflows
   - AI integration helpers

## Quick Start

### Installation

```bash
# Clone marketplace to plugins directory
cd ~/.claude/plugins/marketplaces
git clone https://github.com/vanman2024/low-code-marketplace.git
```

### Example: Cats One → Google Sheets

```bash
# Setup N8N
/n8n:init self-hosted

# Create workflow
/n8n:create-workflow cats-to-sheets
/n8n:add-webhook /applicant-created
/n8n:add-node google-sheets-append sheet=Applicants
/n8n:connect-nodes webhook → sheets
/n8n:deploy-workflow

# Done in 5 minutes!
```

### Example: AI Email Automation

```bash
# Deploy AI email generator (ai-tech-stack)
/vercel-ai-sdk:add-tools email-generator
/fastapi-backend:add-endpoint /generate-email

# Create N8N workflow (low-code)
/n8n:create-workflow ai-email-responder
/n8n:add-webhook /new-email
/n8n:add-node http-request url=your-api.com/generate-email
/n8n:add-node gmail-send-email
/n8n:deploy-workflow
```

## Platform Comparison

| Feature | N8N | Zapier | Make.com |
|---------|-----|--------|----------|
| **Cost** | Free (self-hosted) | $20+/mo | $9+/mo |
| **API Control** | Excellent | Good | Limited |
| **Self-hosted** | Yes | No | No |
| **Apps** | 400+ | 5000+ | 1500+ |
| **Best For** | AI workflows, custom ML | Enterprise, reliability | Budget-friendly |
| **Claude Code Integration** | Best | Good | Moderate |

**Recommendation**: Start with **N8N** for best programmatic control and AI integration.

## Use Cases

### 1. ATS Integration (Cats One)
- Applicant tracking to Google Sheets
- AI-powered candidate screening
- Multi-platform notifications (Slack, Email)
- Resume parsing and enrichment

### 2. Email Automation
- AI-generated personalized responses
- Smart email routing and categorization
- CRM integration with AI insights
- Follow-up automation

### 3. Data Enrichment Pipelines
- Webhook → AI analysis → Multiple destinations
- Real-time data transformation
- AI-powered data quality checks
- Cross-system synchronization

### 4. Event-Driven Workflows
- Trigger workflows from any system
- AI-enhanced decision making
- Multi-step automation chains
- Error handling and retries

## Development Status

**Current Phase**: Planning & Setup
- ✅ Marketplace structure created
- ✅ Planning document complete
- ⏳ N8N plugin (in development)
- ⏳ Zapier plugin (planned)
- ⏳ Make.com plugin (planned)

## Documentation

- [Integration Marketplace Plan](docs/INTEGRATION-MARKETPLACE-PLAN.md) - Complete planning document
- [N8N Plugin Design](docs/N8N-PLUGIN-DESIGN.md) - N8N plugin specification (coming soon)
- [Cross-Marketplace Integration](docs/CROSS-MARKETPLACE.md) - Using with ai-tech-stack (coming soon)

## Contributing

This marketplace is designed to work alongside:
- **dev-lifecycle-marketplace** - Foundation plugins
- **ai-tech-stack-marketplace** - AI application building

Plugins can reference components from other marketplaces for powerful integrations.

## License

MIT

## Contact

- **GitHub**: https://github.com/vanman2024/low-code-marketplace
- **Email**: noreply@low-code-marketplace.dev

---

**Built with Claude Code** 🤖
