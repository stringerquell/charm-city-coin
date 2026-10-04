# The Charm City Coin

The playbook and agent team behind **The Charm City Coin**, a social media brand about business in Baltimore. TBPN for Baltimore business. See `BRAND.md`.

This repo is the one place every AI tool reads from. Claude, Grok, a Claude Project, a scheduled routine: point any of them here and they get the same instructions, the same rules, and the same references.

## What's inside

| Path | What it is | Who reads it |
|---|---|---|
| `BRAND.md` | Who we are, where we come from, what to confirm | Everyone |
| `AGENTS.md` | The rules every tool follows, and what to read first | Every AI tool, first |
| `CLAUDE.md` | Points Claude to `AGENTS.md` | Claude Code |
| `PLAYBOOK.md` | The whole system in plain English: the loop, the crew, the schedule, where Q steps in | Q, and every agent |
| `agents/` | One spec per agent: Scout, Radar, Chief, Writers, Listener, Analyst, Producer | The tool playing that role |
| `templates/` | Source list, scoring rubric, learning ledger, link tagging | Scout, Radar, Analyst, Writers |
| `voice/` | Q's brand voice (files to be added) | Writers, Producer, Chief |
| `references/` | Dated snapshots: Content Ops, Media Block, the original self-learning playbook, the Promenade product | Any agent that needs background |

## How to point a tool at this repo

- **Claude Code / Claude routines:** start the session with this repo selected. Claude reads `CLAUDE.md` on its own.
- **Claude Project:** add this repo as project knowledge (GitHub integration), or upload `AGENTS.md`, `PLAYBOOK.md`, the agent spec, and `voice/`.
- **Grok:** give it the link to `AGENTS.md` and `templates/sources.md`, and tell it it's playing the trend-scanner role.

## Related
- Product (the Promenade): https://github.com/stringerquell/b2b-baltimore
- Strategy (source of truth): Charm City Coin Strategy Doc in Notion
- Content Planner and Newsletter Issues: Notion, under Charm City Coin Content Ops
