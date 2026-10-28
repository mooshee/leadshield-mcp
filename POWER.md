---
name: leadshield
displayName: LeadShield Contact Form & B2B Solicitation Blocker
version: 1.1.1
author: Daniel Hallman
description: 2-stage contact form spam and B2B solicitation blocker for GHL, WP & HubSpot.
keywords:
  - leadshield
  - spam-blocker
  - contact-form
  - b2b-solicitation
  - highlevel
  - gohighlevel
  - wordpress
  - hubspot
  - lead-qualification
  - bot-protection
  - honeypot
  - buyer-intent
  - mcp
mcpServers:
  leadshield:
    type: streamable-http
    url: https://rankandrent-leads.hallmanlab.workers.dev/mcp
---

# LeadShield Contact Form & B2B Solicitation Blocker Power (AWS Kiro)

Author: Daniel Hallman ([Moosh Works](https://mooshworks.com))

2-stage contact form spam and B2B solicitation blocker for GHL, WP & HubSpot. $0.00 Stage 0 deterministic bot drops, Stage 1 buyer-intent screening, server-side per-site policies, and automated weekly spam reports. Built by Moosh Works (https://mooshworks.com).

## Quick start

1. Visit [LeadShield Contact Form & B2B Solicitation Blocker](https://ghlagencymcp.com/use-cases/ghl-contact-form-spam-blocker) or connect Kiro to `https://rankandrent-leads.hallmanlab.workers.dev/mcp`.
2. Built and maintained by [Moosh Works](https://mooshworks.com).

## MCP Server Configuration

```json
{
  "mcpServers": {
    "leadshield": {
      "type": "streamable-http",
      "url": "https://rankandrent-leads.hallmanlab.workers.dev/mcp"
    }
  }
}
```

## Tools Available

- `leadshield_configure_spam_policy`
- `leadshield_generate_guard_embed`
- `leadshield_get_blocked_spam_report`
- `leadshield_get_spam_policy`
- `leadshield_screen_submission`
