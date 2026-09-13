# Data Lifecycle Notes

These notes describe how local prototype data should move through setup, testing, review, and cleanup.

## Seed Data

- `scripts/seed_db.py` creates local demo doctors, appointment slots, callers, and clinic details.
- Seeded records should stay fictional and safe to show in screenshots.
- Rerun the seed script when appointment state makes a test hard to reproduce.
- Avoid editing seeded data manually unless the change is part of a focused test case.

## Runtime Data

- `data/aria.db` stores local prototype state.
- `data/metrics.jsonl` records call outcomes and tool usage.
- `data/feedback.jsonl` stores call feedback for the learning loop.
- `data/latency_log.jsonl` stores timing data for each turn and session summary.

## Review Data

- Use metrics and latency files to identify regressions after demos.
- Keep only sanitized excerpts when sharing findings.
- Remove caller names, phone numbers, appointment notes, and transcript fragments from shared reports.
- Prefer aggregate timing and outcome counts over raw conversation content.

## Cleanup

- Delete local demo data before packaging or presenting the repository outside the development machine.
- Regenerate demo data from the seed script instead of preserving old local state.
- Do not commit runtime database files or generated logs.
