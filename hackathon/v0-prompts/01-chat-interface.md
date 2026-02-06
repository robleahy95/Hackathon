# v0 Prompt 1: Main Chat Interface

Copy-paste this into v0:

---

```
Build a chat interface for a "BD Assistant" that takes actions.

Include:
- A clean header with "BD Assistant" and tagline "I don't just chat. I do things."
- Example prompts shown as clickable chips: "Log a new contact", "Send a follow-up", "Add to pipeline"
- Chat message area showing conversation history with user messages on right, assistant on left
- Input field at bottom with send button
- Use dark mode, minimal design, professional SaaS styling
- Make it responsive for both desktop and mobile
- Use shadcn/ui components

The assistant avatar should be a simple robot/AI icon. User messages should be in a different color than assistant messages.
```

---

## Expected Output

- Full-screen chat interface
- Header with branding
- Message bubbles for conversation
- Input area with send button
- Example prompt chips

## Iteration Prompts (if needed)

**If the chips don't look right:**
```
Make the example prompts into clickable chips that populate the input field when clicked. Style them with a subtle border and hover effect.
```

**If you need better spacing:**
```
Add more padding around messages and make the input area sticky at the bottom of the viewport.
```

**If you want animations:**
```
Add a typing indicator animation when the assistant is "thinking" and smooth scroll when new messages appear.
```
