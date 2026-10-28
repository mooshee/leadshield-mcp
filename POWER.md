---
name: leadshield
displayName: LeadShield Contact Form & B2B Solicitation Blocker
version: 1.1.2
author: Daniel Hallman
description: Filter contact form spam and unwanted sales pitches on HighLevel, WordPress, HubSpot, and custom websites.
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

Filter contact form spam and unwanted sales pitches on HighLevel, WordPress, HubSpot, and custom websites. Set rules for each site and review blocked submissions. Rule-based bot blocking is free; message screening costs $0.01 per submission on the pay-as-you-go plan. Built by Moosh Works (https://mooshworks.com).

## Quick start

1. Open [LeadShield Contact Form & B2B Solicitation Blocker](https://ghlagencymcp.com/use-cases/ghl-contact-form-spam-blocker) for setup instructions.
2. Add `https://rankandrent-leads.hallmanlab.workers.dev/mcp` as an MCP server in Kiro using the configuration below. Complete any required sign-in.
3. Check that the connection lists the plugin's tools before starting a task.

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
