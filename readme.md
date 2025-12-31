# takopi

🐙 *he just wants to help-pi*

telegram bot for [codex](https://github.com/openai/codex). with streaming progress and resumeable sessions.

## features

stateless resume via `codex resume <token>` lines in chat.

edits progress message while codex runs (commands, tools, reasoning, edits, elapsed time).

renders markdown to telegram entities.

runs in parallel across threads and queues per thread to keep codex history sane.

## requirements

- `uv` for installation (`curl -LsSf https://astral.sh/uv/install.sh | sh`)
- `codex` on PATH (`npm install -g @openai/codex` or `brew install codex`)

## install

- `uv tool install takopi` to install as `takopi`
- or try it out with `uvx takopi`

## setup

1. get `bot_token` from [@BotFather](https://t.me/BotFather)
2. get `chat_id` from [@myidbot](https://t.me/myidbot)
2. send `/start` to the bot (telegram won't let it message you first)
3. run `codex` once interactively in the repo to trust the directory

## config

takopi config lives in `~/.takopi/takopi.toml` and can be overriden by `.takopi/takopi.toml` in the current repo.

```toml
bot_token = "123456789:ABCdefGHIjklMNOpqrsTUVwxyz"
chat_id = 123456789

[codex]
# optional: profile from ~/.codex/config.toml
profile = "takopi"
```

## usage

start takopi in the repo you want to work on:

```sh
cd ~/dev/your-repo
takopi
```

send a message to the bot.

to continue a thread, reply to a bot message.

to stop a run, reply to the progress message with `/cancel`.

## cli

by default takopi sends the progress message silently, and replaces it with the final answer to notify you. this can be turned off with `--no-final-notify`

## development

see [`docs/specification.md`](docs/specification.md) and [`docs/developing.md`](`docs/developing.md`).
