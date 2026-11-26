# Flight Control Monitor v3

My Money Team Flight Control. A live board that shows the full automated workflow pipeline, what each agent is doing, if it is online or offline, its progress, its current task, its last message, and who it is talking to. It also shows the 5 money-way agents and the live activity log.

## How live is it, honestly

- This is a static site on GitHub Pages. There is no server, no websocket, no push from GitHub to the browser.
- Live works like this: the page fetches data.json every 15 seconds, and the workflow runner (Muse) updates data.json and pushes it to the repo after every workflow step finishes or starts.
- So the page shows a new step about 15 seconds after Muse pushes the update, plus the time GitHub Pages takes to serve the new file, usually under a minute. It is near live, not instant.
- If a fetch fails, the page keeps the last good data and says so. It never resets counts to zero.
- If no update arrives for 5 minutes, the dot turns amber STALE. Over 30 minutes, red VERY STALE.

## How it works

- Open the page, no login.
- The page reads data.json and fetches it again every 15 seconds, using the refresh_seconds value in data.json.
- Muse is the only updater. Other agents report to Muse, Muse updates data.json, then pushes it to the repo masaugaatho/ai-team-monitor.
- GitHub Pages serves index.html, style.css, and data.json from the main branch root.

## The pipeline

- The top section shows the FundingPips clip 11 chain, 8 steps: 1 Ideas (ChatGPT), 2 Hooks (Claude), 3 Check (DeepSeek), 4 Plan (Gemini), 5 Cut (OpusClip, Vizard, ffmpeg), 6 AI review (Gemini plus DeepSeek), 7 Auto-post (YouTube), 8 Track (Flight Control).
- Each step in data.json has its own status (done, doing, waiting), time, agent, and note, so the runner can update one step without touching the others.
- The whole chain is fully automated end to end. No Saugat review, no human posting step. A clip auto-posts to YouTube once AI review passes, 2 a day max.

## Money ways

- 5 agents in the Money Ways section, each building its first draft: Digital Products (ICT journal pack), Faceless Channel (ICT scripts), Affiliate Shorts (product list), Caption Service (demo pack), Student Job Help (gig text).
- These are Muse subagent teams doing prep work, not separate real AIs, unless a step says a real AI did it. Their cards show the file each one is building.
- Nothing is listed, published, sent, or paid from these ways yet. Drafts only.

## Honest status rules

- An agent is online only when it has a live connection or a verified local tool path in use.
- Offline means NOT CONNECTED YET, not broken.
- Do not mark ChatGPT, Claude, DeepSeek, n8n, Make, OpusClip, Vizard, or CapCut online until the connection is verified.
- Online now: Muse, Gemini, ffmpeg local, Veo via Google Pro, Groq free API, plus the 12 tools signed in on the Muse cloud browser.
- Hailuo is online but has 1 blocked task: cloud browser sign-in failed, retry pending, still signed in on Saugat's laptop.
- n8n is online but not signed in on the cloud browser: it has no Google sign-in, Saugat must type his own password in the cloud browser.
- Earnings stay $0 until real money is confirmed. Never fake money.

## Stale warnings

- Fresh: green LIVE dot.
- Over 5 minutes since last update: amber STALE.
- Over 30 minutes: red VERY STALE.
- If a fetch fails, keep the last good data, do not reset counts to zero.

## Files

- index.html: the board, pipeline, agent cards, log, fetches data.json every 15 seconds.
- style.css: neon dark theme, glassy cards, gradient gauge, pipeline stepper with numbered circles, 15 second refresh, mobile first.
- data.json: meta, pipeline, totals, 23 agents, activity log, newest first, max 50 entries.
- README.md: this file.

## Update flow

1. An agent finishes a step and reports to Muse: what finished, what it sent, who it sent it to, any earnings.
2. Muse updates that pipeline step and that agent, adds one activity log entry, recomputes totals, updates last_updated and version.
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
