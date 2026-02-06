# v0 Prompt 2: Action Confirmation Cards

Copy-paste this into v0 (after prompt 1):

---

```
Add to the chat interface: when the assistant is about to take an action, show a confirmation card inline in the chat.

The confirmation card should include:
- A header showing the action type (e.g., "Adding to Leads")
- Summary of the action with parsed details displayed as a clean list:
  - Name: Sarah Chen
  - Company: Intercom
  - Priority: Hot (with a colored badge)
- Two buttons at the bottom: "✓ Confirm" (primary) and "Edit" (secondary)

After confirmation, replace the card with a success message showing:
- A green checkmark icon
- "Added to Leads"
- A link styled as "View in Notion →"

Keep the same dark mode, minimal design from before.
```

---

## Expected Output

- Inline confirmation card in chat flow
- Parsed data displayed cleanly
- Confirm/Edit button pair
- Success state with checkmark and link

## Iteration Prompts (if needed)

**If the card doesn't stand out enough:**
```
Add a subtle border or different background color to the action card to distinguish it from regular messages.
```

**If you need loading state:**
```
Add a loading spinner that shows between clicking "Confirm" and seeing the success message. The spinner should replace the buttons.
```

**If priority badges need work:**
```
Style the priority badges: Hot = red/orange, Warm = yellow, Cool = blue/gray. Use pill-shaped badges.
```
