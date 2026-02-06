# Tonight's Prep Checklist

## Must Do (2 hours)

### 1. Set up webhook (Make.com is fastest)
- [ ] Create free Make.com account at [make.com](https://make.com)
- [ ] Create new scenario with "Webhook" trigger
- [ ] Add Notion action: "Create a Database Item"
- [ ] Copy webhook URL
- [ ] Test with curl (see webhooks/test-payloads.json)

### 2. Create Notion database for leads
- [ ] Create new Notion database
- [ ] Add columns:
  - Name (Title)
  - Company (Text)
  - Priority (Select: Hot/Warm/Cool)
  - Notes (Text)
  - Date Added (Date)
  - Follow-up By (Date)
- [ ] Share database with Make.com integration
- [ ] Copy database ID for webhook setup

### 3. Test webhook manually
```bash
curl -X POST "YOUR_WEBHOOK_URL" \
  -H "Content-Type: application/json" \
  -d '{"name":"Test Lead","company":"Test Co","priority":"Hot"}'
```

### 4. Draft v0 prompts
- [ ] Review prompts in `v0-prompts/` folder
- [ ] Customize if needed
- [ ] Copy to clipboard for quick paste tomorrow

### 5. Practice demo script
- [ ] Read through `demo/script.md`
- [ ] Practice once out loud (60 seconds)
- [ ] Time yourself

### 6. Sign into v0.app
- [ ] Go to [v0.app](https://v0.app)
- [ ] Create account or sign in
- [ ] Run one test prompt to understand the interface

---

## Nice to Have

- [ ] Create email template for follow-ups
- [ ] Set up second action (email via SendGrid/Resend)
- [ ] Practice pitch two more times
- [ ] Research who from Vercel/Intercom is attending

---

## Day-of Checklist

### Before Event
- [ ] Charge laptop fully
- [ ] Bring charger
- [ ] Have webhook URL ready in notes app
- [ ] Have v0 prompts in notes app (copy-paste ready)
- [ ] Clear browser tabs, fresh workspace

### At Event
- [ ] Arrive at 9am for breakfast networking
- [ ] Execute prompts in v0 during build time (10:00-11:45)
- [ ] Test webhook integration live
- [ ] Deploy before 11:45
- [ ] Volunteer to demo at 1pm

---

## Backup Plan

If webhooks fail or time runs out:
1. Demo the UI with mocked responses
2. Show the CONCEPT of actions, explain what would trigger
3. Say: "In production, this webhook would create the Notion entry"
4. Focus on the vision, not perfect execution

---

## Success Metrics

1. **Ship something deployed** — even if actions are mocked
2. **Demo with confidence** — your script is ready
3. **Memorable pitch** — "the web-native OpenClaw for BD"
4. **3+ connections** — people interested in what you built
5. **Learn v0 + Fin** — skills for future projects
