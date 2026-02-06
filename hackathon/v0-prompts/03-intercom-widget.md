# v0 Prompt 3: Intercom-Style Widget

Copy-paste this into v0 (after prompts 1-2):

---

```
Transform the chat interface into an Intercom-style chat widget. The widget should:

- Appear as a floating circular button (60px) in the bottom-right corner with a chat icon
- When clicked, expand to show the full chat interface as a popup (400px wide, 600px tall)
- Have a header with "BD Assistant" and an X button to minimize
- Keep all the existing chat functionality (messages, confirmation cards, success states)
- Have "Powered by Fin" text at the bottom of the widget
- Add a subtle shadow and rounded corners to the expanded widget
- Animate smoothly when opening/closing

The floating button should have a pulse animation to draw attention initially.
```

---

## Expected Output

- Floating action button in corner
- Expandable chat widget
- Smooth open/close animation
- "Powered by Fin" branding
- All previous functionality preserved

## Iteration Prompts (if needed)

**If animation is choppy:**
```
Use CSS transitions with ease-out timing for the expand/collapse animation. The widget should scale and fade in from the button position.
```

**If you want a badge:**
```
Add a notification badge on the floating button that shows "1" to indicate a new message or prompt.
```

**If mobile needs work:**
```
On mobile, make the expanded widget full-screen instead of a popup. Add a slide-up animation.
```

---

## Alternative: Full-Page with Widget Feel

If the widget approach is too complex for the time limit, use this simpler prompt:

```
Keep the full-page chat interface but add:
- "Powered by Fin" footer text
- Intercom-style gradient on the header (purple to blue)
- More rounded corners on message bubbles
- The overall aesthetic should feel like an Intercom product
```
