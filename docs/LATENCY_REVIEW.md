# Latency Review Checklist

Use this checklist after a manual demo or automated test run to understand where conversational delay is coming from.

## Collect Evidence

- Save the command used to start the bot.
- Note whether the run used WebRTC, Twilio, Daily, or another transport.
- Capture the local timestamp of the call.
- Review `data/latency_log.jsonl` after the call ends.

## Inspect Turn Timing

- Compare after-STT latency across the first, middle, and final turns.
- Look for repeated LLM time-to-first-token spikes.
- Check whether TTS time-to-first-byte is slow only on long responses.
- Separate provider latency from local infrastructure time when the log includes both.

## Review Conversation Shape

- Long tool explanations can hide latency improvements, so compare response length with timing.
- Repeated clarification questions may indicate prompt or tool-schema friction.
- Interruptions and cutoffs often point to VAD or endpointing settings.
- Slow first responses may come from provider warmup rather than steady-state behavior.

## Follow-up Actions

- Record a minimal caller phrase that reproduces the slow path.
- Link timing notes to the feature or tool flow being tested.
- Prefer one latency change at a time so improvements are measurable.
- Update diagnostics when a new repeatable bottleneck is found.
