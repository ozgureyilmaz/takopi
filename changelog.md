# changelog

## v0.1.0 (2025-12-29)

initial release.

### features

- telegram bot bridge for openai codex cli using `codex exec` and `codex exec resume`
- stateless session resume via `resume: <uuid>` lines embedded in messages
- real-time progress updates with ~2s throttling, showing commands, tools, and elapsed time
- full markdown rendering with telegram entity support (via markdown-it-py + sulguk)
- concurrent message handling with per-session serialization to prevent race conditions
- automatic telegram token redaction in logs
- interactive onboarding guide for first-time setup
- cli options: `--profile`, `--debug`, `--final-notify`, `--version`
