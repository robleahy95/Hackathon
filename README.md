# Astra — BD Assistant That Takes Action

> A web-based BD assistant that doesn't just chat — it logs leads, sends follow-ups, and updates your pipeline. Built with v0, powered by Fin.

Built in 80 minutes at the [v0 Prompt to Production](https://v0.dev) hackathon @ Intercom London, Feb 2026.

## The Problem

You're at a conference. 20 conversations, scribbled notes, lost context. Follow-up falls through the cracks. CRMs are databases — nobody opens Salesforce between sessions to fill forms.

## The Solution

Tell Astra what happened in natural language. It handles the rest.

```
You:   "Log Sarah from Intercom as a hot lead"
Astra:  Confirms → Logs to Google Sheets → Done
```

No forms. No tab switching. No manual data entry.

## How It Works

```
[User input] → [Fin extracts intent] → [Webhook] → [Google Sheets]
                                                        ↓
                                                  Live update visible
```

| Layer | Tool |
|-------|------|
| Frontend | v0-generated chat UI with confirmation cards |
| AI | Intercom Fin (intent extraction) |
| Actions | Make.com webhook → Google Sheets API |
| Hosting | Vercel |

## Demo

Split screen — chat on the left, Google Sheet on the right. Say "Log Sarah from Intercom as a hot lead", confirm the action, and watch the row appear live.

## Project Structure

```
hackathon/
├── v0-prompts/              # Prompts used to generate the UI in v0
│   ├── 01-chat-interface.md
│   ├── 02-action-confirm.md
│   └── 03-intercom-widget.md
├── webhooks/
│   ├── setup-guide.md       # Webhook + Sheets wiring guide
│   └── test-payloads.json   # Sample payloads for testing
├── demo/
│   ├── script.md            # 60-second demo script
│   └── pitch.md             # Pitch positioning + Q&A prep
├── BATTLE-PLAN.md           # 80-minute build timeline
├── checklist.md             # Prep checklist
└── day-of-quickref.md       # Day-of quick reference card
```

## Built With

- [v0](https://v0.dev) — UI generation from prompts
- [Intercom Fin](https://www.intercom.com/fin) — Conversational AI
- [Make.com](https://www.make.com) — Webhook automation
- [Google Sheets API](https://developers.google.com/sheets/api) — Live data store
- [Vercel](https://vercel.com) — Deployment

## License

MIT
