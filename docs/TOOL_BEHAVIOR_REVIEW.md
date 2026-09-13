# Tool Behavior Review

Use this checklist when changing or reviewing tool-calling behavior in Aria.

## Intent Matching

- Confirm the caller phrase maps to the intended tool before changing handler code.
- Test direct requests and natural variations, such as "I need to see a doctor" or "Can someone call me back?"
- Keep medical advice and emergency language routed to escalation.
- Avoid calling scheduling tools when the caller only asks a general clinic question.

## Inputs

- Ask for missing required details one at a time.
- Normalize phone numbers before lookup, reminder, or appointment operations.
- Confirm date and time values before writing appointment changes.
- Keep free-text notes short and avoid sensitive details.

## Outputs

- Summarize tool results without exposing internal identifiers.
- Explain unavailable slots by offering the next useful step.
- For records and reminders, describe staff follow-up instead of promising instant fulfillment.
- If a tool error occurs, offer escalation rather than repeatedly retrying in conversation.

## Regression Checks

- Run the related tests after changing a tool schema or handler.
- Add a manual phrase to `docs/TEST_CHECKLIST.md` when a new behavior is introduced.
- Review logs for raw payloads before sharing test output.
