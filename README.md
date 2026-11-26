# Flight Control Monitor v2

My Money Team Flight Control. A live board that shows what each agent is doing, if it is online or offline, its progress, its current task, its last message, and who it is talking to.

## How it works

- Open the page, no login.
- The page reads data.json and fetches it again every 30 seconds.
- Muse is the only updater. Other agents report to Muse, Muse updates data.json, then pushes it to the repo masaugaatho/ai-team-monitor.
- GitHub Pages serves index.html, style.css, and data.json from the main branch root.

## Honest status rules

- An agent is online only when it has a live connection or a verified local tool path in use.
- Offline means NOT CONNECTED YET, not broken.
- Do not mark ChatGPT, Claude, DeepSeek, n8n, Make, OpusClip, Vizard, or CapCut online until the connection is verified.
- Online now: Muse, Gemini, ffmpeg local, Veo via Google Pro, Groq free API backup.
- Earnings stay $0 until real money is confirmed. Never fake money.

## Stale warnings

- Fresh: green LIVE dot.
- Over 5 minutes since last update: amber STALE.
- Over 30 minutes: red VERY STALE.
- If a fetch fails, keep the last good data, do not reset counts to zero.

## Files

- index.html: the board, fetches data.json every 30 seconds.
- style.css: dark theme, mobile first.
- data.json: meta, totals, 13 agents, activity log, newest first, max 50 entries.
- README.md: this file.

## Update flow

1. An agent finishes a task and reports to Muse: what finished, what it sent, who it sent it to, any earnings.
2. Muse updates that agent, adds one activity log entry, recomputes totals, updates last_updated and version.
3. Muse pushes data.json to masaugaatho/ai-team-monitor.
4. The page picks up the new data within about a minute.

## Connection order, one by one

1. ChatGPT first, browser sign in as Saugat, free chat.
2. Claude second, browser sign in as Saugat, free chat, Sonnet and Haiku only.
3. DeepSeek third, browser sign in, free chat, API is paid only.
4. n8n fourth, self hosted Community free, or Make free 1,000 credits a month.
5. Groq fifth, free API key in Secure Vault, backup text and Whisper.
6. Then Perplexity, OpenRouter free, OpusClip, Vizard, CapCut, NotebookLM Pro.

No passwords or API keys in chat, in files, or in the repo. Browser sign in or Secure Vault only.
