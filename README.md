# LeadShield Contact Form & B2B Solicitation Blocker MCP

[![LeadShield MCP](https://img.shields.io/badge/LeadShield%20MCP-v1.1.0-blue.svg)](https://ghlagencymcp.com/use-cases/ghl-contact-form-spam-blocker)
[![LeadShield MCP server quality and maintenance on Glama](https://glama.ai/mcp/servers/mooshee/leadshield-mcp/badges/score.svg)](https://glama.ai/mcp/servers/mooshee/leadshield-mcp)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

> **Author**: Daniel Hallman  
> **Website**: [ghlagencymcp.com/use-cases/ghl-contact-form-spam-blocker](https://ghlagencymcp.com/use-cases/ghl-contact-form-spam-blocker)  
> **Remote MCP Endpoint**: `https://rankandrent-leads.hallmanlab.workers.dev/mcp` (`streamable-http`)  
> **Official MCP Registry ID**: `io.github.mooshee/leadshield`  

LeadShield is a 2-stage contact form spam and B2B cold-pitch solicitation blocker for GoHighLevel (GHL), WordPress, HubSpot, and custom websites. It stops SEO pitches, web-design solicitors, offshore lead-gen agencies, and automated form bots before they trigger client SMS/email alerts or pollute CRM pipelines — while silently returning `"Message sent"` to spammers so bots never adapt or retry.

## Quick start

1. Visit [LeadShield Contact Form & B2B Solicitation Blocker](https://ghlagencymcp.com/use-cases/ghl-contact-form-spam-blocker) for architecture diagrams, CRM setup guides, and policy presets.
2. Connect any MCP client to `https://rankandrent-leads.hallmanlab.workers.dev/mcp` (`streamable-http`), or install directly in your preferred host:
   - **VS Code (1-Click MCP)**: [Install LeadShield MCP in VS Code](https://insiders.vscode.dev/redirect/mcp/install?name=leadshield&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Frankandrent-leads.hallmanlab.workers.dev%2Fmcp%22%7D)
   - **Claude Code**: `/plugin marketplace add mooshee/leadshield-mcp` then `/plugin install leadshield@leadshield`
   - **Gemini CLI**: `gemini extensions install https://github.com/mooshee/leadshield-mcp`
   - **Devin CLI**: `devin plugins install mooshee/leadshield-mcp`
   - **Vercel Skills (`skills.sh`)**: `npx skills add mooshee/leadshield-mcp`
   - **ClawHub**: `clawhub install leadshield-form-spam-blocker`

---

## Core Capabilities (5 Live MCP Tools)

### 1. 2-Stage Contact Form Screening (`leadshield_screen_submission`)
- **Stage 0 Deterministic Edge Drop (`$0.00` / 0 billable units)**: Blocks honeypot fills, sub-1.2s automated fills, disposable emails, link shorteners, promotional URLs, foreign phone prefixes, and known B2B solicitation templates in under 1 ms.
- **Stage 1 Buyer-Intent Classification (`$0.01/submission` on Pay-As-You-Go)**: Evaluates human-written messages that pass Stage 0 to separate genuine local customers asking for a quote or appointment from vendors pitching services.
- Returns `allowed`, `blocked`, `verdict` (`verified_lead` or `blocked_spam`), `branch` (`deliver_to_client` or `spam_quarantine`), `stage`, `category`, `reason`, and `customerProbability`.

### 2. Blocked Spam Reports & Weekly Audit Summaries (`leadshield_get_blocked_spam_report`)
- Query quarantined contact form spam counts, Stage 0 vs Stage 1 breakdowns, and top spam categories (`link_solicitation`, `b2b_solicitation`, `geographic_mismatch`, `bot_honeypot`) by client slug and date window.

### 3. Server-Side Policy Inspection & 10 Form-Type Presets (`leadshield_get_spam_policy`)
- Inspect effective per-site rules and preview any of the 10 built-in `formType` presets (`general_inquiry`, `quote_request`, `booking_request`, `b2b_partnership`, `support_ticket`, `careers_application`, `warranty_claim`, `event_registration`, `newsletter_signup`, `feedback_review`).

### 4. Custom Country, Phone Format, URL & Keyword Policy Configuration (`leadshield_configure_spam_policy`)
- Preview (`dryRun: true`) or update server-side policies (`allowedCountries`, `allowedPhoneFormats`, `blockUrlsInMessage`, `maxUrls`, `blockedKeywords`, `requiredKeywords`) stored in R2 so browser scripts never expose filter heuristics.

### 5. Zero-Trust Script Embed & CRM Webhook Generator (`leadshield_generate_guard_embed`)
- Generate the 1-line `<script src="https://rankandrent-leads.hallmanlab.workers.dev/guard.js" data-site="..." defer></script>` tag, HighLevel Workflow Action config, WordPress plugin setup, or HubSpot Workflow Webhook config.

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
