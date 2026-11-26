# My Money Team, Live Monitor

A simple free GitHub Pages site that shows Saugat what each AI agent is doing, live.

Live site: https://masaugaatho.github.io/ai-team-monitor/

## What it shows

- Money at a glance: goal $1,000, earned so far, still to go, with a wide bar
- Today counts: Finished, Working, Stuck
- 11 agent cards, Working first, each with a plain sentence, status, current task, and tools
- Task list: Finished and Working
- Money earned: real money only, never fake money

No login. No passwords. No private emails, addresses, phone numbers, or dates of birth in this repo.

## How it stays live, without Saugat doing anything

The page reads `data.json` in this repo. It refreshes that file every 60 seconds.

When a team finishes a task, Muse updates `data.json` in GitHub with the new status, task, and earnings, if any. The page then shows the new data on the next refresh. Saugat only needs to open the page and look. He does not need to press anything, edit anything, or log anything.

## How Muse updates it

1. A team finishes work and reports back with what is done and what is next.
2. Muse edits `data.json` in this repo: agent `status` and `current_task`, task `status` done or doing, `earnings_usd` and the earnings list only when real money arrives, and `last_updated` to now.
3. GitHub Pages rebuilds the site in about a minute. The page auto refreshes every 60 seconds, so the new data appears without a manual reload.
4. Never put passwords, private emails, addresses, phone numbers, or dates of birth in `data.json` or in any file here.

## Files

- `index.html` : the page, mobile first, one column
- `style.css` : simple colours, green Working, blue Finished, amber Stuck
- `data.json` : the live data, agents, tasks, earnings, goal, last updated time
- `README.md` : this guide
