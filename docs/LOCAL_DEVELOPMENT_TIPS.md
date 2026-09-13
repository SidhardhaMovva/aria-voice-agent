# Local Development Tips

These tips help keep local Aria development predictable while working on voice, tools, and observability.

## Environment Setup

- Prefer the project virtual environment created by `uv sync`.
- Keep `.env` local and copy new keys from `.env.example` when configuration changes.
- Restart the bot after changing prompt, provider, transport, or database settings.
- Use `127.0.0.1` instead of `localhost` when browser audio connection behavior is inconsistent.

## Daily Workflow

- Pull the latest `main` before starting a change.
- Run focused tests for the module you touched before running the full suite.
- Keep sample caller data fictional in tests, logs, and manual notes.
- Check the documentation table in `README.md` when adding a new guide.

## Debugging Habits

- Reproduce failures with the shortest caller phrase possible.
- Capture the command, branch, provider settings, and local timestamp for each bug.
- Separate provider outages from code regressions before changing implementation.
- Review generated metrics after any manual voice demo.

## Clean Workspace

- Do not commit local databases, generated logs, virtual environments, or provider credentials.
- Delete temporary artifacts after using them for screenshots or demos.
- Keep commits scoped to one behavior, guide, or test update at a time.
