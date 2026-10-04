# Self-Learning Directory Site Playbook (original)

> **Snapshot taken Oct 1, 2026** from Google Drive: `self-learning-directory-site-playbook.md` (https://drive.google.com/file/d/1vPwsjPsEFCiMOQzP-rB-Q2vxR0kfGMK6/view).
> This is the engineer's original, written for a local events directory built with Grok Bot. `PLAYBOOK.md` at the root of this repo is the Charm City Coin adaptation. Keep this file as the reference, not the plan.

### Build and grow a local directory with Grok Bot (strategy, sequence, prompts)

Shareable version. No product names, emails, keys, or infra secrets. Swap in your niche, city, and tools.

---

## 1. What you are building

A **self-learning local directory**: a site that lists real-world things people search for in one city (events, places, providers, etc.), then gets smarter every week through agents that:

1. **Scout** new inventory from public sources
2. **Publish** sanitized listings (with human merge OK for code)
3. **Rank and explain** via SEO hubs + guides
4. **Capture demand** (email list) and **nurture** (digest)
5. **Listen** to social/search demand and feed the next content
6. **Show receipts** with a public growth page (optional)

"Self-learning" here means a closed loop: observe demand → refresh inventory → ship content → measure → decide the next experiment. Not unsupervised writes to production without gates.

---

## 2. Roles (one founder + specialist bots)

Keep roles thin so prompts stay sharp.

| Role | Owns |
|------|------|
| **Ops / coding bot** | Repo PRs, ingest scripts, dashboards, routines, merge only after your OK |
| **Scout bot** | Daily/weekday candidate lists from public platforms (recommend-only by default) |
| **Writer bot** | Guides, digest copy, social paste packs, welcome email |
| **Inbox / admin** (optional) | Mail triage, calendar; not product copy |

Rule: **you post** on social and newsletter schedule unless you explicitly say otherwise. Agents draft paste-ready assets.

---

## 3. Stack pattern (generic)

Pick one of each. Exact vendors do not matter; the loop does.

- **App:** Next.js (or similar) + Postgres
- **Hosting:** managed frontend + managed DB
- **Analytics:** GA4 (or equivalent) + Search Console
- **Email:** newsletter platform with free-subscriber audience + welcome automation
- **Source control:** GitHub + cloud coding agents for PRs
- **Agent desk:** Grok Bot with routines, skills, cloud agents for repo work

Hard rules worth copying:

- Never invent acceptance criteria mid-flight
- Never merge without founder OK
- Never store secrets in chat; use a locked env file on the agent computer
- Store times as true UTC; display in local zone
- No automated social posting unless you opt in

---

## 4. Sequence (do this order)

### Phase 0 — Decide the wedge (1 sitting)

Lock before code:

1. **Niche** (who + what + city)
2. **Primary job-to-be-done** (e.g. "find something to do this weekend with people")
3. **Inventory unit** (event, venue, listing) and required fields
4. **Trust bar** (ticket URL required? age range? paid only?)
5. **North-star metric** (visitors → signups → return visits)

**Prompt:**

```
We are building a local directory for [CITY] focused on [NICHE].
Primary user job: [JOB].
Inventory unit: [EVENT/VENUE/LISTING].
Must-have fields: [LIST].
Trust bar: [e.g. ticket URL required, no seed/fake rows in public boards].
North star: [metric].
Draft a one-page product brief and a Definition of Ready checklist before any code.
```

---

### Phase 1 — Thin vertical slice (ship something real)

Ship:

- City hub (`/city`)
- "This weekend" board
- Detail pages with ticket outbound links
- Postgres models + public read API

Skip: accounts, payments, comments, multi-city.

**Prompt:**

```
Using our AI coding playbook, open a PR for Phase 1 only:
- City hub + this-weekend board + detail pages
- Postgres models for [UNIT] + organizer
- Public list API with a sane cap
- Ticket URL required for board inclusion
DoR first (7 gates). Model: latest Grok for cloud agents.
Do not invent AC. Stop for my OK before merge.
```

---

### Phase 2 — Scout loop (the learning engine)

Add a **weekday scout routine**:

1. Search public platforms for new candidates
2. Diff against live inventory
3. Recommend top N with links, times, prices
4. **Recommend-only** until you say "ingest these"

After OK, ingest with true UTC conversion and dedupe rules (same ticket URL + new date = new occurrence / update, not a silent overwrite).

**Prompt (routine):**

```
Weekday scout for [CITY] [NICHE].
Sources: [platforms].
Compare to live inventory via [API or DB read].
Return top 10 net-new candidates: title, date/time local, venue, price, ticket URL, short note.
Recommend-only. No DB writes. Skip weak or already-listed. Ask if I want any ingested.
```

**Prompt (ingest after OK):**

```
Ingest these approved ticket URLs into prod.
Convert local wall times to true UTC.
Dedupe by ticket URL + date.
Spot-check live detail pages after write. Report what landed and what failed.
```

---

### Phase 3 — Email capture + welcome + weekend digest

1. Capture placements on hubs + soft popup (copy from writer bot)
2. Sync signups to newsletter platform (best-effort)
3. Welcome email: who you are, why you built it, what they get, one CTA
4. Thursday routine: build Friday-scheduled weekend digest from live ticketed inventory

**Prompt (welcome):**

```
Draft a fun, very brief welcome email from the founder.
Audience: people who joined the [CITY] list.
Include: thanks, personal why (human connection / easier to find real-world [THINGS]), expectations (weekend digest, rare midweek notes, no spam), one link to the this-weekend board.
No em dashes. Paste-ready for [newsletter tool] welcome automation.
```

**Prompt (digest routine):**

```
Every Thursday: pull Fri–Sun ticketed [UNITS] for [CITY] from the live API.
Build a plum-on-brand HTML digest + notes file.
Subject includes the weekend date range.
Primary CTA: View on site. Secondary: Get tickets.
Schedule for Friday afternoon local. Do not send now.
If newsletter login expired, prepare files and ask me to sign in.
```

---

### Phase 4 — SEO hubs and guides (compounding pages)

Pattern that works:

1. **Hub pages** with answer block → filters/chips → listings → popular guides
2. **Guides** that map to search intent (season, age band, vibe, neighborhood)
3. Internal links both ways
4. Request indexing after merge
5. Striking-distance pass from Search Console every few weeks

**Prompt (guide sprint):**

```
SEO content sprint for [CITY] [NICHE].
Pick the next guide from: [intent backlog].
Use live inventory only; be honest if the season is thin.
Follow existing guide pattern (title/meta, FAQ JSON-LD, email capture, no emoji in H1s, no em dashes).
Open a draft PR. Stop for merge OK. After live, request Search Console indexing.
```

---

### Phase 5 — Demand listening (social + search)

Agents **research and draft**; you **post**.

- Mine Reddit / forums / X for threads where a helpful reply + UTM link fits
- Paste-ready comments only; no bot account posting
- Prefer a multi-platform read/search toolkit when auth works; fall back to web search mining

**Prompt:**

```
Mine public [CITY] discussions about [NICHE] for reply opportunities.
For each: URL, why it fits, risk notes, paste-ready comment with UTM to our this-weekend or guide page.
I post myself. Do not log into my social accounts or comment.
```

---

### Phase 6 — Measurement and public receipts

Weekly scoreboard:

- Visitors / pageviews (7d)
- Top pages
- Email subscribers (DB vs newsletter, reconcile)
- Live inventory count

Optional: public `/build-in-public` page

- KPIs + top pages (paths only, never identity)
- Sanitized decisions / experiments
- Subscriber chart from product-start week (no empty padded history)
- Soft footer link; not in main nav
- Auto-publish ledger notes after sanitize (no founder queue), still merge OK for code

**Prompt:**

```
Plan a public build-in-public page: pulse KPIs, top pages, subscriber growth from [product start week], what shipped, sanitized experiments.
Indexable, soft footer link only, Off-brand design tokens.
Auto-publish sanitized ledger items. Open PR. Merge only on my OK.
```

---

## 5. Operating system (keep forever)

### Definition of Ready (front-load)

Before non-trivial work: goal, users, success metric, in/out of scope, data sources, risks, stop conditions.

### Decision rubric

For non-trivial choices: options → tradeoffs → recommendation → what would change your mind.

### Evidence-first review

PRs need: what changed, how verified (lint/tsc/checks), what was not tested (e.g. no DB in CI).

### Gates you should not skip

| Gate | Who |
|------|-----|
| Merge code | Founder OK |
| Ingest to prod | Founder OK (or standing allow-list) |
| Send newsletter | Founder OK or explicit "schedule it" |
| Public social post | Founder posts |
| Ledger sanitize rules | Agreed once, then auto |

---

## 6. Prompt kit (copy/paste)

**Stand up coding standards**

```
Add our AI SDLC coding skill to this bot.
On every coding/PR/design task: frontload DoR, decision rubric, execute the contract, evidence-first review.
Cloud agents: use model [latest Grok]. Never invent AC mid-flight. Never merge without my OK.
```

**Lock product facts in memory**

```
Remember for this product:
- City + niche + primary URLs
- Timezone rules (store UTC, show local)
- Newsletter design rules (palette, fonts, CTA hierarchy)
- Content bans (e.g. no em dashes, no emoji in headings)
- Social: paste-ready only; I post
Do not store secrets in memory; point to a locked env path on the agent computer.
```

**Weekly growth scoreboard**

```
Every Monday: pull 7d visitors/pageviews, top pages, subscriber totals (DB + newsletter), live inventory count.
One short scoreboard message. Flag anomalies. Propose one experiment.
```

**When blocked on login**

```
If a dashboard session expired, prepare the asset files, tell me what is ready, and offer to open the agent desktop for sign-in. Do not invent a send.
```

---

## 7. 30-day starter plan

| Week | Focus | Exit criteria |
|------|--------|----------------|
| 1 | Phase 0–1 | Live hub + board + detail pages with real ticket links |
| 2 | Scout + ingest | Weekday scout routine; first approved ingest batch |
| 3 | Capture + digest | Signup path live; welcome draft; one scheduled weekend digest |
| 4 | SEO + listen | 1–2 guides live + indexed; one social paste pack shipped by you |

Then repeat: scout → ingest → guide or hub refresh → digest → measure → next experiment.

---

## 8. What "self-learning" looks like in practice

```
Demand signal (search / Reddit / GA top pages)
 ↓
Scout finds inventory that matches the signal
 ↓
You approve ingest
 ↓
Guide or hub answers the query with live links
 ↓
Digest and social send people back
 ↓
Scoreboard + public ledger show what worked
 ↓
Next week's scout and content backlog update
```

Agents close the loop. You keep the keys: merge, ingest, send, post.

---

## 9. Sanitize checklist before you share this playbook

- [ ] No customer emails or personal names beyond "founder"
- [ ] No API keys, connection strings, or hostnames
- [ ] No proprietary ticket-platform account details
- [ ] Replace city/niche examples with placeholders if needed
- [ ] Keep vendor names generic if you prefer ("newsletter platform")

---

*Built from a real local-directory build loop with Grok Bot. Adapt freely.*
