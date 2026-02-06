# 80-MINUTE BATTLE PLAN

**Start time:** ___:___ | **Must ship by:** ___:___

---

## PHASE 1: FOUNDATION (15 min)
**Timer: 0:00 - 0:15**

### 1A. Google Sheet Setup (5 min)
- [ ] Create new Google Sheet: "BD Assistant Leads"
- [ ] Add headers in Row 1:
  ```
  A: Timestamp | B: Name | C: Company | D: Status | E: Source
  ```
- [ ] Make sheet publicly viewable (for demo visibility)
- [ ] Keep tab open — this is your demo's "proof it works"

### 1B. Make.com Webhook (10 min)
- [ ] Go to make.com → Create new scenario
- [ ] Add trigger: **Webhooks → Custom webhook**
- [ ] Name: "BD Lead Capture" → Save → **Copy URL**
- [ ] Add action: **Google Sheets → Add a Row**
- [ ] Connect Google account
- [ ] Select your "BD Assistant Leads" sheet
- [ ] Map fields:
  - Column A (Timestamp): `{{now}}`
  - Column B (Name): `{{1.name}}`
  - Column C (Company): `{{1.company}}`
  - Column D (Status): `{{1.status}}`
  - Column E (Source): `"BD Assistant"`
- [ ] Click "Run once" → Keep it waiting for data
- [ ] Test with curl:
  ```bash
  curl -X POST "YOUR_WEBHOOK_URL" \
    -H "Content-Type: application/json" \
    -d '{"name":"Test","company":"TestCo","status":"Hot"}'
  ```
- [ ] Verify row appears in Sheet
- [ ] Turn scenario ON → Set to "Immediately"

**Checkpoint:** Webhook → Sheet working? Move on.

---

## PHASE 2: v0 UI BUILD (25 min)
**Timer: 0:15 - 0:40**

### 2A. Chat Interface (15 min)
Paste into v0:
```
Build a minimal chat interface for "Astra" - a BD assistant that takes real actions.

Requirements:
- Clean header: "Astra" with subtitle "I don't just chat. I take action."
- Chat area with user messages (right, blue) and assistant messages (left, gray)
- One example chip: "Log Sarah from Intercom as hot lead"
- Input field + send button at bottom
- Dark mode, professional, shadcn/ui
- When user sends message, show typing indicator then assistant response

Make it feel premium and minimal. Desktop-first.
```

Iterate if needed:
- "Make the chip clickable and populate the input when clicked"
- "Add a subtle gradient to the header"

### 2B. Action Confirmation Card (10 min)
Add to v0:
```
Now add an action confirmation card that appears when the assistant is about to take an action.

The card should:
- Slide in below the assistant message
- Show: "Ready to log lead" with details (Name: Sarah, Company: Intercom, Status: Hot)
- Have two buttons: "Confirm" (green) and "Cancel" (gray)
- When confirmed, show a success state with checkmark
- Animate smoothly

This replaces the normal message when an action is detected.
```

**Checkpoint:** UI looks good in v0 preview? Move on.

---

## PHASE 3: WIRE IT UP (25 min)
**Timer: 0:40 - 1:05**

### 3A. Export & Deploy v0 (5 min)
- [ ] Click "Code" in v0 to export
- [ ] Deploy to Vercel (one-click from v0)
- [ ] Get your live URL
- [ ] Test it loads

### 3B. Add Webhook Call (15 min)
In v0 or exported code, add this to the Confirm button:
```typescript
const handleConfirm = async () => {
  setLoading(true);

  await fetch('YOUR_MAKE_WEBHOOK_URL', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
      name: leadData.name,      // "Sarah"
      company: leadData.company, // "Intercom"
      status: leadData.status    // "Hot"
    })
  });

  setSuccess(true);
  setLoading(false);
};
```

- [ ] Replace YOUR_MAKE_WEBHOOK_URL with actual URL
- [ ] Test: Click confirm → Check Sheet updates

### 3C. Hardcode Demo Flow (5 min)
For hackathon, hardcode the happy path:
```typescript
// When user types anything containing "Sarah" or "log"
if (message.toLowerCase().includes('sarah') || message.toLowerCase().includes('log')) {
  // Show the action card with:
  setLeadData({ name: 'Sarah', company: 'Intercom', status: 'Hot' });
  setShowActionCard(true);
}
```

**Checkpoint:** Full flow works? Demo time.

---

## PHASE 4: DEMO PREP (15 min)
**Timer: 1:05 - 1:20**

### 4A. Setup Demo View (5 min)
- [ ] Open browser with two windows side by side:
  - LEFT: Your app (full deployed URL)
  - RIGHT: Google Sheet (visible, empty except headers)
- [ ] Clear any test data from Sheet
- [ ] Zoom browser to ~125% for visibility

### 4B. Rehearse 3 Times (10 min)
Script:
1. "This is Astra, a BD assistant that takes real action"
2. Click the example chip OR type: "Log Sarah from Intercom as a hot lead"
3. Point: "It understood my intent and is asking to confirm"
4. Click Confirm
5. Point to Sheet: "And there it is — real data, real action"
6. "Built in 80 minutes with v0. Questions?"

Practice transitions. Know your timing.

---

## EMERGENCY FALLBACKS

**If webhook fails during demo:**
- Have Sheet pre-populated with 2-3 leads
- Say "let me show you one I logged earlier"
- Demo still works conceptually

**If v0 deploy fails:**
- Use v0 preview mode (still works, just not "production")
- Deploy to Vercel manually if needed

**If Make.com is slow:**
- Add a delay in your success state
- Say "it updates in real-time" (it will, just delayed)

---

## SUCCESS CRITERIA

Before you present, verify:
- [ ] Type message → Action card appears
- [ ] Click confirm → Sheet updates within 5 seconds
- [ ] Demo script takes under 60 seconds
- [ ] You can explain it in one sentence: "It's a BD assistant that actually logs leads to your CRM when you ask"

---

**GO BUILD. CLOCK STARTS NOW.**
