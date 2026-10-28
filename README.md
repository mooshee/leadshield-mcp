# LeadShield Contact Form & B2B Solicitation Blocker MCP

[![LeadShield MCP](https://img.shields.io/badge/LeadShield%20MCP-v1.1.2-blue.svg)](https://ghlagencymcp.com/use-cases/ghl-contact-form-spam-blocker)
[![LeadShield MCP server quality and maintenance on Glama](https://glama.ai/mcp/servers/mooshee/leadshield-mcp/badges/score.svg)](https://glama.ai/mcp/servers/mooshee/leadshield-mcp)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

Author: Daniel Hallman ([Moosh Works](https://mooshworks.com))

- **Website**: [LeadShield](https://ghlagencymcp.com/use-cases/ghl-contact-form-spam-blocker)
- **Remote MCP Endpoint**: `https://rankandrent-leads.hallmanlab.workers.dev/mcp` (`streamable-http`)
- **Official MCP Registry ID**: `io.github.mooshee/leadshield`

LeadShield filters contact form spam and unwanted sales pitches on HighLevel, WordPress, HubSpot, and custom websites. Set rules for each site and review blocked submissions before deciding whether to change them.

## Quick start

1. Open the [LeadShield setup guide](https://ghlagencymcp.com/use-cases/ghl-contact-form-spam-blocker) and choose your website or CRM.
2. Connect a client that supports Streamable HTTP MCP to `https://rankandrent-leads.hallmanlab.workers.dev/mcp`, or choose an installation option below.
3. Check the intended site's active rules with `leadshield_get_spam_policy` before changing them.

Installation options:

   - **VS Code (1-Click MCP)**: [Install LeadShield MCP in VS Code](https://insiders.vscode.dev/redirect/mcp/install?name=leadshield&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Frankandrent-leads.hallmanlab.workers.dev%2Fmcp%22%7D)
   - **Claude Code**: `/plugin marketplace add mooshee/leadshield-mcp` then `/plugin install leadshield@leadshield`
   - **Gemini CLI**: `gemini extensions install https://github.com/mooshee/leadshield-mcp`
   - **Devin CLI**: `devin plugins install mooshee/leadshield-mcp`
   - **Vercel Skills (`skills.sh`)**: `npx skills add mooshee/leadshield-mcp`
   - **ClawHub**: `clawhub install leadshield-form-spam-blocker`

---

## What you can do

### Screen a form submission (`leadshield_screen_submission`)

- **Free bot checks:** Block submissions that match configured rules for hidden fields, fill speed, disposable emails, links, or sales-pitch phrases.
- **Message screening:** Check the remaining messages against the business description. This costs $0.01 per submission on the pay-as-you-go plan.
- Returns `allowed`, `blocked`, `verdict` (`verified_lead` or `blocked_spam`), `branch` (`deliver_to_client` or `spam_quarantine`), `stage`, `category`, `reason`, and `customerProbability`.

### Review blocked submissions (`leadshield_get_blocked_spam_report`)

Choose a site and date range to see blocked counts, screening stages, and reasons.

### Check site rules (`leadshield_get_spam_policy`)

Read the site's active rules and `formType` preset. Use the values returned by the tool when choosing a preset.

### Change site rules (`leadshield_configure_spam_policy`)

Preview changes with `dryRun: true`. After an authorized update, read the policy again to confirm the saved country, phone, link, and keyword rules. Rules are stored on the server.

### Add LeadShield to a site or workflow (`leadshield_generate_guard_embed`)

Generate setup instructions for a website script, HighLevel workflow action, WordPress plugin, or HubSpot webhook. Replace the site placeholder with the intended site identifier, then test a form submission and check the result.

---

## MCP Configuration (`mcp.json`)

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

## License

MIT License — see [LICENSE](LICENSE).

## Package and review status

The included OpenAI review draft still needs a verified recording and provider checks before submission. Installing this package does not submit it to a directory.

## Release notes

[Version 1.1.2 — October 28, 2026](https://github.com/mooshee/leadshield-mcp/releases/tag/v1.1.2) clarifies descriptions, screening prices, example prompts, and setup checks. Existing connections and features are unchanged. Update your plugin or skill to load the revised instructions.
