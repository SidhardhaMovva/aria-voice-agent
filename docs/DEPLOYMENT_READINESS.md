# Deployment Readiness Notes

Aria is a working prototype. Use these notes before sharing a hosted demo or planning a production-style deployment.

## Prototype Demo Readiness

- Confirm the demo uses synthetic caller and appointment data.
- Verify API keys are provided through environment variables, not committed files.
- Run the health check after provider, network, or container changes.
- Confirm the WebRTC client can connect from the target browser.

## Runtime Review

- Check startup logs for missing provider keys and port conflicts.
- Confirm latency logs are being written for each test session.
- Verify staff handoff paths produce clear tickets or follow-up notes.
- Make sure repeated failed tool calls lead to escalation instead of a loop.

## Security and Privacy Gaps

- Do not treat the prototype as HIPAA-compliant.
- Add authentication before exposing real caller records.
- Define log retention, redaction, encryption, and access controls before real clinic use.
- Review vendor agreements and data handling before integrating production providers.

## Rollback Plan

- Keep the previous known-good commit available before a demo.
- Note configuration changes separately from code changes.
- Capture the exact command and environment used for any successful run.
- Revert demo-only configuration changes before continuing feature work.
