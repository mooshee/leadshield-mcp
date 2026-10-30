---
name: leadshield
displayName: LeadShield Contact Form & B2B Solicitation Blocker
version: 1.1.3
author: Daniel Hallman
description: Preview contact form screening, manage connected-site rules, review retained blocked messages, and generate setup instructions. Built by Moosh Works (https://mooshworks.com).
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

# LeadShield Contact Form & B2B Solicitation Blocker for Kiro

Author: Daniel Hallman ([Moosh Works](https://mooshworks.com))

Preview contact form screening, manage connected-site rules, review retained blocked messages, and generate setup instructions. Screening previews do not store or deliver leads or process payments. Built by Moosh Works (https://mooshworks.com).

## Quick start

1. Open [LeadShield Contact Form & B2B Solicitation Blocker](https://ghlagencymcp.com/use-cases/ghl-contact-form-spam-blocker) for setup instructions.
2. Add `https://rankandrent-leads.hallmanlab.workers.dev/mcp` as an MCP server in Kiro using the configuration below. Sign in and grant access to the intended sites.
3. Use `leadshield_get_spam_policy` to confirm access to the intended site. Follow the [screening instructions](skills/leadshield-form-spam-blocker/SKILL.md) for previews, saved-rule checks, pricing, and installation limits.

## Server configuration

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

## Available tools

- `leadshield_configure_spam_policy`
- `leadshield_generate_guard_embed`
- `leadshield_get_blocked_spam_report`
- `leadshield_get_spam_policy`
- `leadshield_screen_submission`
