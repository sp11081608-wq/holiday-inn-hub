# OpenRouter Usage Limits (standing rules)
*(saved July 14, 2026 — details in ~/Documents/Setup/HANDOFF.md §7 and SETUPCHANGELOG.md "Credits Audit — July 12, 2026". Updated July 14, 2026 — model retirement.)*

- This CLI runs on OpenRouter **:free models** (nemotron for Opus/Sonnet) — they bill **$0**. Caps: **20 requests/min, 1000 requests/day** (unlocked by the July 8, 2026 $10 purchase).
- A SessionStart hook runs the credits check; **if it shows a WARNING, tell the user immediately in plain language.** If hook output is absent, run `~/.claude/scripts/check-openrouter-credits.sh` early.
- **429 errors = daily/minute request cap hit.** Explain plainly: resume tomorrow (resets daily) or switch model.
- **Ignore `/cost` output** — it's an estimate at Anthropic prices, not a real charge; free models bill $0.
- **`anthropic/claude-sonnet-4.5` was RETIRED June 15, 2026.** For important work needing a paid model for one session: `claude --model anthropic/claude-sonnet-5` (paid for that session only, back to free when closed). Do not suggest sonnet-4.5 anymore.
- Free models often **fail to write files in headless `-p` mode** — any scripted/non-interactive run that needs to write files should use `--model anthropic/claude-sonnet-5`, not a free model.
- The API key lives only in `~/.zshrc` — never print or copy it into documents.
- Shyam conserves usage: don't run big builds unless he says go.
