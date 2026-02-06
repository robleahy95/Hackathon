# v0 Prompt to Production Hackathon

**Event:** v0 Prompt to Production IRL @ Intercom London
**Date:** Feb 6, 2026 (tomorrow)
**Format:** ~2 hours building time, demos at lunch

---

## Project: Web-Based Agentic BD Assistant

**Concept:** A web app that doesn't just chat — it DOES things.

**Differentiator:** Web-native, no install, built with sponsor tools (v0 + Fin).

**Track:** GTM (Go-to-Market)

---

## Why This Can Win

| Factor | How this project delivers |
|--------|---------------------------|
| **v0 showcase** | Built entirely with v0 prompts — "prompt to production" in 2 hours |
| **Fin showcase** | Fin as agentic intelligence, not just FAQ bot |
| **Novel use case** | Fin for BD automation, not customer support |
| **Trend alignment** | Agentic AI is the moment (OpenClaw just went viral) |
| **Authentic story** | You live this problem — BD chaos, manual follow-ups |
| **Demo impact** | "Watch: I tell it to do X → it actually does X" |

---

## What It Does

| Request | Action |
|---------|--------|
| "Log Sarah from Intercom as a hot lead" | Creates record via webhook (Notion/Sheets) |
| "Send follow-up to John about partnership" | Triggers email via webhook |
| "Add Vercel to my research pipeline" | Updates tracking spreadsheet |

---

## Directory Structure

```
hackathon/
├── README.md                 # This file
├── v0-prompts/
│   ├── 01-chat-interface.md  # Main chat UI prompt
│   ├── 02-action-confirm.md  # Action confirmation cards
│   └── 03-intercom-widget.md # Intercom-style widget
├── webhooks/
│   ├── setup-guide.md        # Webhook setup instructions
│   └── test-payloads.json    # Test data for webhooks
├── demo/
│   ├── script.md             # 60-second demo script
│   └── pitch.md              # Pitch positioning
└── checklist.md              # Tonight's prep checklist
```

---

## Quick Links

- [v0 Prompts](./v0-prompts/)
- [Demo Script](./demo/script.md)
- [Tonight's Checklist](./checklist.md)
- [Webhook Setup](./webhooks/setup-guide.md)

---

## Technical Architecture

```
[User] → [v0-built UI] → [Fin conversation] → [Webhook] → [Action]
                                                  ↓
                                          • Notion API
                                          • Email service
                                          • Google Sheets
```
