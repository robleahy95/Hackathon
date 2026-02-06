# Alternative Project Options

If the main BD Assistant concept doesn't resonate or you want a backup, here are fully-documented alternatives.

---

## Option A: Startup Support Portal (Product Track) — RECOMMENDED BACKUP

**The Problem:**
Early-stage startups can't afford a support team, but their first customers need help. They're stuck choosing between slow email support or expensive headcount. Fin changes this equation — 59% of queries resolved without humans.

**Why this wins:**
- Perfect Fin alignment — shows exactly what Intercom sells to startups
- Your SAP experience — you managed support and escalations
- Startups Program tie-in — you're demo-ing what they get for free in year 1
- Metric-driven — shows "X% resolved by Fin" which is Intercom's sales pitch

### User Flow

```
Screen 1: Customer-Facing Help Center
┌─────────────────────────────┐
│  🏠 YourStartup Help        │
│                             │
│  How can we help you?       │
│                             │
│  [_________________________]│
│  [Ask Fin →]                │
│                             │
│  Popular topics:            │
│  • Getting started          │
│  • Billing & payments       │
│  • Integrations             │
│  • Account settings         │
│                             │
│  ─────────────────────────  │
│  💬 Chat with Fin           │
│  🕐 Usually responds in <1m │
└─────────────────────────────┘

Screen 2: Fin Chat in Action
┌─────────────────────────────┐
│  💬 Chat with Fin           │
│                             │
│  You: "How do I connect     │
│       my Stripe account?"   │
│                             │
│  Fin: "To connect Stripe:   │
│  1. Go to Settings →        │
│     Integrations            │
│  2. Click 'Add Stripe'      │
│  3. You'll be redirected    │
│     to authorize access     │
│                             │
│  Need the full guide?       │
│  [View docs →]              │
│                             │
│  ✅ Resolved                │
│  [👍 Helpful] [👎 Not quite]│
└─────────────────────────────┘

Screen 3: Escalation Flow
┌─────────────────────────────┐
│  💬 Chat with Fin           │
│                             │
│  You: "I was charged twice  │
│       for my subscription"  │
│                             │
│  Fin: "I understand billing │
│  issues are frustrating.    │
│  I've found your account    │
│  and see two charges on     │
│  Feb 3.                     │
│                             │
│  This needs a human to      │
│  issue a refund. I'll       │
│  connect you now — I've     │
│  already shared the context │
│  so you won't repeat        │
│  yourself.                  │
│                             │
│  [Connecting to support...] │
└─────────────────────────────┘

Screen 4: Founder Dashboard
┌─────────────────────────────┐
│  📊 Support Dashboard       │
│  This week                  │
│                             │
│  Queries received: 127      │
│  Resolved by Fin: 81 (64%)  │
│  Escalated to human: 46     │
│                             │
│  ███████████░░░░░░░ 64%     │
│  Fin Resolution Rate        │
│                             │
│  Top resolved topics:       │
│  • Getting started (23)     │
│  • Integrations (19)        │
│  • Password reset (15)      │
│                             │
│  💰 Saved this week:        │
│  ~12 hours of support time  │
│  (= $360 at $30/hr)         │
└─────────────────────────────┘
```

### v0 Prompts

**Prompt 1 — Help Center:**
```
Build a customer-facing help center homepage for a SaaS startup.
Include: a search bar with "Ask Fin" button, 4 popular topic cards
(Getting started, Billing, Integrations, Account settings), and a
floating chat widget prompt saying "Chat with Fin — usually responds
in <1 minute." Use clean, modern SaaS styling with white background.
```

**Prompt 2 — Fin Chat Resolved:**
```
Create a chat interface showing a customer asking "How do I connect
my Stripe account?" and Fin AI responding with numbered steps.
Include a "Resolved" status at the bottom with thumbs up/down
feedback buttons. Show Fin's avatar as a simple AI icon. The chat
should feel conversational and helpful.
```

**Prompt 3 — Escalation:**
```
Show a chat where the customer says "I was charged twice" and Fin
acknowledges the issue, explains it needs a human for refunds, and
says "I'll connect you now — I've shared the context so you won't
repeat yourself." Show a "Connecting to support..." status. This
demonstrates smart escalation, not robotic dead-ends.
```

**Prompt 4 — Dashboard:**
```
Build a founder-facing support dashboard. Show: total queries (127),
resolved by Fin (81, 64%), escalated (46). Include a progress bar
for Fin resolution rate. List top resolved topics with counts.
Add a "Saved this week" section showing hours saved and dollar
equivalent. Make it feel like a founder checking metrics quickly.
```

### Demo Script (60 seconds)

> "You're a startup with 200 customers and zero support staff.
> Before Fin, you're stuck answering emails at midnight.
> [Show help center] Now customers come here and ask Fin directly.
> [Show resolution] Fin answers 'How do I connect Stripe?' with
> step-by-step instructions. Resolved. No human needed.
> [Show escalation] When it's a billing dispute, Fin knows to
> escalate — but passes the context so the customer doesn't
> repeat themselves.
> [Show dashboard] And as the founder, I see this: 64% of queries
> resolved by Fin this week. That's 12 hours I didn't spend on
> support — $360 saved.
> This is exactly what the Intercom Startups Program gives you
> for free in year one."

---

## Option B: Event Contact Capture (GTM Track)

**The Problem:**
You're at a conference, have a great conversation, scribble notes on a napkin, then later can't remember who was "the guy from the payments company who wanted an intro." Follow-up falls through the cracks.

**Why this wins:**
- You've lived this — 30+ meetings sourced at events
- Intercom's team runs events (like this hackathon) — they'll relate
- Mobile-first = you demo on your phone, which is memorable
- You can use it at the event itself (meta demo)

### User Flow

```
Screen 1: Quick Capture (mobile-first)
┌─────────────────────────────┐
│  + New Contact              │
│                             │
│  Name: [____________]       │
│  Company: [____________]    │
│  Role: [____________]       │
│                             │
│  Conversation Notes:        │
│  [________________________] │
│  [________________________] │
│                             │
│  Priority: 🔥 Hot  🟡 Warm  ⚪ Cool │
│                             │
│  Follow-up by: [date picker]│
│                             │
│  [Save & Add Another]       │
└─────────────────────────────┘

Screen 2: Lead Dashboard
┌─────────────────────────────┐
│  Event: v0 Hackathon        │
│  Feb 6, 2026 | 12 contacts  │
│                             │
│  Filter: [All] [🔥] [🟡] [⚪] │
│                             │
│  ┌─────────────────────┐    │
│  │ Sarah Chen          │    │
│  │ Intercom - PM       │🔥  │
│  │ "Interested in..."  │    │
│  │ Follow up: Tomorrow │    │
│  └─────────────────────┘    │
│                             │
│  ┌─────────────────────┐    │
│  │ James Miller        │    │
│  │ Vercel - DevRel     │🟡  │
│  │ "Building agent..." │    │
│  │ Follow up: Feb 10   │    │
│  └─────────────────────┘    │
└─────────────────────────────┘

Screen 3: Intercom Integration
┌─────────────────────────────┐
│  Automated Follow-up        │
│                             │
│  When priority = 🔥 Hot:    │
│  → Send LinkedIn request    │
│  → Trigger Intercom message │
│     within 24 hours         │
│                             │
│  When priority = 🟡 Warm:   │
│  → Add to nurture sequence  │
│  → Intercom email in 3 days │
│                             │
│  [Configure Intercom →]     │
└─────────────────────────────┘
```

### v0 Prompts

**Prompt 1 — Capture Form:**
```
Build a mobile-first contact capture form for networking events.
Include fields: name, company, role, conversation notes (textarea),
priority selector (hot/warm/cool with emoji icons), and a date
picker for follow-up deadline. Use a clean, minimal design with
dark mode. Add a "Save & Add Another" button that clears the form
after saving. Make it feel fast to use.
```

**Prompt 2 — Dashboard:**
```
Create a dashboard showing captured contacts from events. Include:
- Event name and date at top
- Filter chips for priority (All, Hot, Warm, Cool)
- Contact cards showing name, company, role, truncated notes,
  priority indicator, and follow-up date
- Cards should be tappable to expand full details
- Sort by follow-up date (soonest first)
Use the same dark mode style as the capture form.
```

**Prompt 3 — Intercom Integration:**
```
Add a settings page showing Intercom integration options. Display:
- Connection status with Intercom (show a green "Connected" badge)
- Automation rules: "When priority is Hot, trigger Intercom message
  within 24 hours" / "When priority is Warm, add to nurture sequence"
- A button to "Configure in Intercom" (can be a placeholder link)
Keep it simple — this is about showing the integration concept.
```

### Demo Script (60 seconds)

> "I've sourced 30+ qualified meetings at conferences. The problem?
> Capturing context in the moment and following up reliably.
> [Show phone] This lets me capture a contact in 10 seconds — name,
> company, what we talked about, how hot the lead is.
> [Show dashboard] Later, I see everyone from an event, filtered by
> priority. No more lost napkin notes.
> [Show integration] And here's where Intercom comes in — hot leads
> get an automated follow-up within 24 hours. Warm leads enter a
> nurture sequence. I never drop the ball.
> Built this morning with v0. It's deployed. I'm going to use it
> for everyone I meet today."

---

## Option C: Customer Onboarding Wizard (Product Track)

**The Problem:**
New customers sign up, then get lost. They don't complete setup, don't see value quickly, and churn.

**Why it works:**
- Your process improvement track record (70% → 95% compliance KPIs at Utmost)
- Natural fit for Fin as contextual help
- Product track = fewer developers competing

### User Flow

```
Screen 1: Welcome + Progress
┌─────────────────────────────┐
│  Welcome, Sarah! 👋         │
│                             │
│  Let's get you set up.      │
│  This takes about 5 minutes.│
│                             │
│  ████████░░░░░░░░ 40%       │
│                             │
│  ✅ Create account          │
│  ✅ Verify email            │
│  🔵 Connect your data       │ ← Current
│  ⚪ Invite team members     │
│  ⚪ Set preferences         │
│                             │
│  [Continue →]               │
│                             │
│  💬 Need help? [Chat with Fin] │
└─────────────────────────────┘
```

### v0 Prompts

**Prompt 1 — Onboarding Shell:**
```
Build a customer onboarding wizard with a progress bar and step
checklist. Show 5 steps: Create account (done), Verify email (done),
Connect your data (current), Invite team members, Set preferences.
Include a progress percentage at the top. Add a floating "Need help?
Chat with Fin" button in the corner. Use a clean, modern SaaS style
with a white background and subtle shadows on cards.
```

**Prompt 2 — Fin Chat Integration:**
```
Add an Intercom-style chat widget that slides up from the bottom.
Show a sample conversation where the user asks "Which data source
should I choose?" and Fin (the AI) gives a helpful, contextual
response about Salesforce vs CSV. Include "This helped" and
"Talk to human" feedback buttons.
```

---

## Decision Framework

| If you want... | Choose... |
|----------------|-----------|
| Most aligned with your BD story | Main project (BD Assistant) |
| Safest Intercom alignment | Option A (Support Portal) |
| Most memorable demo | Option B (Event Capture on phone) |
| Least competitive track | Option C (Onboarding Wizard) |
