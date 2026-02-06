# Hackathon Project Context

## WHY - Purpose

Building a **Web-Based Agentic BD Assistant** for the v0 Prompt to Production Hackathon (Intercom London, Feb 6, 2026).

**Goal:** Win with ONE undeniable "wow moment" — user says "Log Sarah from Intercom as a hot lead" → assistant confirms → Google Sheet updates LIVE on screen.

**Track:** GTM (Go-to-Market)

## WHAT - Narrowed Scope (Critical)

**Single workflow:** Lead logging to Google Sheets
**Single integration:** Google Sheets API only
**Single wow moment:** Live data appearing during demo

- **Frontend:** v0-generated chat UI with action confirmation card
- **AI Brain:** Intercom Fin (extracts intent: name, company, status)
- **Action Layer:** Your app executes webhook → Google Sheets append
- **Demo visual:** Split screen — chat left, Sheet updating right

```
Architecture:
[User input] → [Fin extracts intent] → [Your app] → [Sheets API] → [Live update visible]
```

## HOW - Working in This Project

**Build sequence:**
1. v0: Generate chat UI + confirmation card (~20 min)
2. Sheets: Create sheet + get API credentials (~10 min)
3. Webhook: Wire up intent → Sheets append (~25 min)
4. Fin: Configure as conversation brain (~15 min)
5. Polish + rehearse demo (~10 min)

**Key files:**
- `hackathon/v0-prompts/` - UI generation prompts
- `hackathon/webhooks/setup-guide.md` - Webhook configuration
- `hackathon/demo/script.md` - 60-second demo flow

## Universal Guidelines

- ONE workflow only — resist feature creep
- If it's not in the demo, don't build it
- The "wow moment" is the entire product
- Google Sheets visible during demo = proof it works
