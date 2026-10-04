# The Charm City Coin Newsroom
### A self-learning media engine for Baltimore business

Adapted from the *Self-Learning Directory Site Playbook* (Google Drive) for what Charm City Coin actually is, per the Strategy Doc in Notion (current direction: Sept 27 and Sept 29, Oct 1 launch play).

Written for Q. No engineering knowledge needed to read this. Any AI tool should read `AGENTS.md` first. The `agents/` folder holds the specs the agents run on. The `templates/` folder holds the source list, the scoring rubric, and the learning ledger.

---

## 1. The one-paragraph version

The playbook was written for a directory: agents find events, list them, and the site gets smarter every week. We are not building a directory. We are building a **newsroom that teaches itself.** Agents scan Baltimore's public records, local news, and event calendars every morning. They rank what they find, write angles in your lens, and turn the angle you pick into an X thread, a Threads post, an IG carousel, a LinkedIn post, a newsletter section, and an SEO article. Every piece links back to the newsletter (and later the Promenade). Every Sunday, an analyst agent looks at what worked, writes down the lessons, and changes how Scout ranks stories and how Chief writes angles the next week. That last step is what makes it "self-learning." You keep four keys: **pick the angle, post, send, merge.**

---

## 2. What changes from the original playbook

| Directory playbook | Charm City Coin newsroom |
|---|---|
| Inventory unit: an event listing | **An item:** one sourced Baltimore business fact (a filing, a permit, a contract award, a bid, an opening, an event, a headline) |
| Goal: list everything | **Goal: say something about it.** Aggregation is the raw material; Q's take is the product |
| Scout finds listings, you approve ingest | Scout finds items, **Chief writes angles, you pick one** (that's where your take goes in) |
| Publish = a listing page | Publish = **one story, six formats** (X, Threads, IG, LinkedIn, newsletter, SEO article) |
| SEO hubs = "things to do this weekend" | SEO hubs = **The Radar** (weekly public-data roundups) + **evergreen guides** for owners |
| Weekend digest email | **Monday "This Week"** (mostly automated) + **Thursday "The Take"** (yours) + weekly show |
| North star: visitors → signups | **Oct goal: 1,000 newsletter subscribers.** Long term: introductions that turned into paid work |
| Directory is the product | **The Promenade is the showroom and bottom of the funnel.** Media drives people to it, the city never fills itself with public data |

What we keep exactly as written: the closed loop, recommend-only defaults, human gates, "never invent a number," and the weekly scoreboard.

---

## 3. The loop

```
 ┌──────────────────────────────────────────────────────────────────┐
 │                                                                  │
 ▼                                                                  │
LISTEN ── what owners ask, search, reply, click                     │
 │                                                                  │
SCOUT ─── 7am: rank 8-10 Baltimore items, with links               │
 │        (weights come from the Learning Ledger)                   │
 │                                                                  │
CHIEF ─── 2-3 angles for the top 3, in Q's lens                     │
 │                                                                  │
Q PICKS ─ voice note, ~5 min. Your take goes in here.  [KEY 1]      │
 │                                                                  │
WRITERS ─ one story → X thread, Threads, IG, LinkedIn,              │
 │        newsletter section, SEO article. Voice gate on all.       │
 │                                                                  │
Q POSTS ─ copy, paste, post, paste the URL back.  [KEY 2]           │
 │        Newsletter send [KEY 3]. Site changes [KEY 4].            │
 │                                                                  │
MEASURE ─ views, saves, shares, follows, subscribers, clicks        │
 │                                                                  │
LEARN ─── Sunday: Analyst writes 3-5 lessons + 1 experiment ────────┘
          into the Learning Ledger. Scout and Chief read it Monday.
```

---

## 4. The crew (seven agents)

The Strategy Doc has three slightly different agent lists from Sept 24, 27, and the Media Block. This merges them into one crew. Full specs live in `agents/`, written in the format the doc asks for: role, goal, inputs, process, quality bar.

| # | Agent | Runs | Does | Writes to |
|---|---|---|---|---|
| 1 | **Scout** | Daily 6:30am | Scans news, public records, events. Dedupes. Scores with the rubric. Top 8-10 items. | Content Planner as 💡 Idea |
| 2 | **Radar** | Weekly, Sunday night | Compiles the public data (new filings, permits, liquor apps, contract awards, bids, businesses for sale) into one dataset | Radar page in Notion; feeds Monday issue + SEO Radar article |
| 3 | **Chief** | Daily 7:15am | 2-3 angles for the top 3 items, in your lens; one question to pull your take | Planner → 🎯 Angles; morning ping to you |
| 4 | **Writers** | After you pick | Turns the picked angle + your take into the six formats; runs the voice gate | Planner → 👀 Ready for Q |
| 5 | **Listener** | Daily light, weekly report | Mines replies, comments, DMs, Reddit, Search Console, survey answers, Promenade searches for demand | Demand section of the weekly report; new Ideas |
| 6 | **Analyst** | Sunday | Scoreboard, what worked, lessons, next experiment | Learning Ledger + Sunday report |
| 7 | **Producer** | Weekly (script Sat, edit Sun) | The weekly founder short (events rundown, your face and voice) + Thursday show clips | Planner as Reel / Short; script to Slack |

Plus the **Builder** (Claude Code, this repo), on demand only: SEO pages on the Charm City Coin site (domain TBD), UTM links, analytics, Radar hub. Opens pull requests; never merges without you.

### Claude or Grok?

The Sept 27 decision still holds, and I'd keep it:

- **Claude runs the engine.** Scout, Radar, Chief, Writers, Analyst, and the Builder. Anything that needs your voice, Baltimore depth, public records, Notion, or Beehiiv. Claude can run these as scheduled routines with Notion and Beehiiv connected, so they fire on their own every morning.
- **Grok does one job: real-time X and web trends.** It's the best tool for "what is Baltimore talking about on X right now." It drops its finds into the same Notion digest Scout uses, tagged `source: grok-trends`. It does not write.
- **Notion is the handoff point.** Nothing moves between tools except through the Content Planner.

---

## 5. A day and a week

### Daily (your time: 20-30 minutes)

| Time | What happens | Who |
|---|---|---|
| 6:30 | Scout scans, scores, drops 8-10 items in the Planner | Agent |
| 6:45 | Grok adds 2-3 trending X/web items (optional) | Agent |
| 7:15 | Chief writes angles for the top 3, sends you a short "pick one" message | Agent |
| Your morning | **You pick by voice note** (e.g. "1B, 3A. My take on 1: ..."). 5 min. | **Q** |
| +20 min | Writers produce the pack; voice gate runs; status → 👀 Ready for Q | Agent |
| Your choice | **You post** (X, Threads, IG, LinkedIn) and paste the URL back | **Q** |
| Daily | Events post on Threads (already running; Scout now feeds it) | Agent drafts, Q posts |

### Weekly

| Day | What | Who |
|---|---|---|
| **Saturday** | Producer sends the founder short script to Slack | Agent |
| **Sunday** | **You record the short** (5-10 min on your phone). Producer edits it that night. | **Q** + agent |
| **Sunday night** | Radar compiles the week's public data. Analyst writes the scoreboard and the lessons. Listener files the demand report. | Agents |
| **Monday** | **Founder short goes out** on Reels, TikTok, Shorts, Threads, X, LinkedIn. "This Week" newsletter: events + Radar headlines + buzz. Mostly assembled by agents the night before. **You skim and hit schedule.** Radar SEO article goes up. | Agents + **Q sends** |
| **Tuesday-Wednesday** | Evergreen SEO guide drafted from the backlog | Agents, **Q approves** |
| **Thursday** | "The Take" newsletter + the weekly show (from Oct 8). Your feature. Clips for X and Threads. | **Q** + agents for clips/packaging |
| **Friday** | Next week's batchable pieces drafted (takes, recaps, reviews) | Agents |

---

## 6. One story, six formats

Each picked angle becomes a **content pack**. Templates for each are in `agents/04-writers.md`. Short version:

| Format | Shape | CTA (October default: Subscribe) |
|---|---|---|
| **X thread** | 5-8 posts. Post 1 = the hook with the number. Middle = what happened, receipts, why it matters. Last = your take + newsletter link. | Link in final post |
| **Threads** | 1-3 short posts, conversational. Ends with a question (replies feed the Listener). | Link in bio / reply |
| **Instagram** | 4:5 carousel brief in Design brief v2 (white, ink, one orange element, Goldman/Archivo headline). Caption + "Comment OUTLOOK" keyword when relevant. | Comment keyword |
| **LinkedIn** | Your voice, first person, work-hours framing. Uses the `linkedin-authority-post` skill. | Subscribe or none |
| **Newsletter section** | The Rundown format already in Content Ops: headline → the rundown → the details → why it matters. | Built in |
| **SEO article** | Answer block up top, sourced facts, your take, FAQ, newsletter signup, link to the Promenade where relevant. | Signup box |

**Plus one weekly video: the founder short.** Separate from the daily packs. Every Monday, a 30-60 second vertical video: you on camera for the open, your voice over cards for 3-5 of the week's coworking and networking events, back on camera for your pick, then "full list in the newsletter." Working title "Who's Working This Week" or "Where to Work This Week" (your call). It's the one piece every week that has your face on it, which is what aggregator pages don't have. Producer handles the script, event cards, edit (Descript), and captions. Later, once the format is set, it can run on an AI double of you (ElevenLabs voice + HeyGen), labeled as AI per platform rules. Full spec: `agents/07-producer.md`.

Not every story gets all six. Chief tags which formats fit. A contract award fits X + newsletter + Radar article. A new coworking space fits IG + Where to Work.

---

## 7. What makes it "self-learning" (the important part)

The loop learns through three things the agents read before every run. All three live in Notion so you can see and override them.

**1. The Scoring Rubric** (`templates/scoring-rubric.md`). Scout scores every item 0-100 on things like: is there a dollar figure, a named neighborhood, a named business, is it ground-level, is it fresh, does it fit a lane. Each factor has a **weight**. The weights start as my best guess.

**2. The Learning Ledger** (`templates/learning-ledger.md`). Every Sunday the Analyst compares what was posted against how it did and writes 3-5 plain-English lessons, each with the evidence. Examples of the kind of lesson it writes (illustrations, not real data yet):
> *"Contract-award stories with a dollar figure in the hook got 2x the saves of ones without. Raise `has_dollar_figure` weight from 10 to 15."*
> *"Threads posts that ended in a question got 3x replies. Keep."*
> *"LinkedIn posts about permits underperformed 3 weeks in a row. Stop sending permits to LinkedIn."*

The Analyst also **proposes** the weight changes. You approve them with a yes in the Sunday report (or set a standing rule like "auto-apply changes under 5 points").

**3. The Experiment slot.** One experiment a week, written as: *we think X, we'll test it by Y, we'll know by Z.* Example: "Lead the Monday issue with the Radar instead of events; measure open-to-click." The Analyst reports the result the next Sunday and it goes into the Ledger either way.

Over a month, Scout stops surfacing what your audience ignores, Chief leans toward the angles that land, and Writers stop using hooks that flop. That's the loop.

**What we measure** (most of these fields already exist in the Content Planner):
- Already there: Views, Saves, Shares, Follows Gained, Posted URL
- To add: **Subscribers driven** (from Beehiiv UTM), **Link clicks**, **Replies**, **Hook type**, **Scout score**, **Promenade clicks**
- Weekly from outside: Beehiiv subscribers and open/click rates, Search Console queries, site visits, Outlook downloads

---

## 8. SEO: the compounding layer

Social posts disappear in 48 hours. Search pages keep sending people for years. Two kinds of pages:

**The Radar (recurring, weekly).** One page per week: "New Baltimore businesses, permits, and contract awards: week of Oct 5." Built from public data only. Searchers looking for leads and news find it; the free version shows headlines and your take, the full list is the member product later. Freshness + a page every week = topical authority.

**Evergreen guides (backlog-driven).** Answer what owners actually search. Starter backlog:
- How to bid on Baltimore City contracts (CitiBuy, eMMA, Board of Estimates explained)
- Baltimore business networking events: the weekly guide
- Small business grants and loans in Baltimore (banks, CDFIs, city programs)
- Where to work in Baltimore: coworking and meeting spaces (Where to Work lane)
- Businesses for sale in Baltimore: how to find them
- New business openings in Baltimore, by neighborhood
- Money on the Move: where Baltimore businesses can sell in 2027 (the Outlook, as a public summary that gates the full report)

Every article: answer block in the first 100 words, every fact linked, one FAQ section, newsletter signup, and a link to a relevant Promenade landmark or member plot. Listener feeds new topics from Search Console and the questions people ask on Threads.

**Where the articles live.** My recommendation: **start on the Beehiiv website** (zero engineering, already indexable, signup built in). Move the Radar hub to [Charm City Coin domain, TBD]/radar once the domain is live and the weekly cadence is steady, so the domain that hosts the Promenade earns the search credit. The Builder does that move as a pull request.

**What we never claim:** that anyone will rank on Google because of us. That rule is already in the doc for members; it applies to our own articles too.

---

## 9. How the content drives people to the Promenade

The doc is clear: **public data goes in the newsletter, not into the city as unclaimed buildings.** So the connection is links and landmarks, not filling the map.

- **October:** every CTA is Subscribe. The newsletter footer carries "walk the city" and the Block 01 seat count.
- **Editorial landmarks:** when we cover an institution (e.g. the Lewis Museum recap), it can get a free, clearly labeled landmark in the city that links back to the story. Stories link to the landmark.
- **Members:** when a story mentions a member, link their plot (`/plot/1`). Members reshare.
- **Radar → membership:** free Radar shows headlines; the full filterable list is a member perk. Every Radar page ends with "the full list is part of a Block seat."
- **UTMs on every link** so the Analyst can tell which story sent who. Convention in `templates/utm-convention.md`.

---

## 10. The rules (from your doc, enforced by every agent)

1. **Never invent** a number, quote, source, deal, event, or experience. Every claim carries a link. Unverified = flagged, not posted.
2. **Credit when someone else broke it** ("via BBJ," "via the Banner"). Read paywalled sources, never copy them. Go to the same primary records they use.
3. **Permission-first names an order of operations, not people.** Never knock a specific program, agency, or institution.
4. **Public data only.** Never add anyone to a list without their say-so.
5. **Label everything paid.** Sponsors never buy coverage. Disclose Quickship every time it appears.
6. **Every size, every industry.** The corner store and the $40M contractor in the same feed.
7. **Your voice bans apply to every draft** (the voice gate checks `voice/brand-voice.md`). No em dashes.
8. **No auto-posting.** Agents draft paste-ready assets. You post.

### Your four keys

| Gate | Who |
|---|---|
| Pick the angle (your take) | Q |
| Post to social | Q |
| Send or schedule the newsletter | Q (or explicit "schedule it") |
| Merge site code | Q |
| Weight changes in the Ledger | Q approves, or a standing rule |
| Everything else (scan, score, draft, compile, report) | Agents, automatic |

---

## 11. Rollout (revised Oct 1: public start Monday, Oct 5)

Nothing has gone public yet, and Oct 1 is a Thursday. So we set up Thursday and Friday, do a dry run over the weekend, and go public on **Monday, Oct 5**, which matches the Monday "This Week" / Thursday "The Take" rhythm. The 30-day run becomes **Oct 5 to Nov 4**. The first show stays Thursday, Oct 8.

| When | Turn on | Done when |
|---|---|---|
| **Thu-Fri, Oct 1-2** | Rename the IG account to the Charm City Coin handle (TBD) (Threads follows). Beehiiv: rename the publication, fix the default signup flow, Day 0 welcome email live. Create Slack `#charm-desk`. | A stranger can follow, subscribe, and get a welcome email |
| **Sat-Sun, Oct 3-4** | Dry run: Scout, Radar, and Chief run for real. You pick in Slack Sunday. Writers build Monday's pack and Issue 1. | Monday's posts and Issue 1 are waiting for you |
| **Week 1 · Oct 5-11** | Public launch Monday. First founder short Monday (if recorded Sunday; otherwise it starts Oct 12). Daily Scout + Chief + Writers. Thursday: The Take + first show. Rest of the welcome sequence. | 5 mornings in a row with picks waiting; launch post + 2 issues out |
| **Week 2 · Oct 12-18** | Radar SEO article weekly on Beehiiv web. Listener starts. Outlook turned into 10 posts. | First Radar page live |
| **Week 3 · Oct 19-25** | Analyst + first Learning Ledger entry. Twice-weekly sends. | First lesson written, first weight change |
| **Week 4 · Oct 26-Nov 4** | 2 evergreen SEO guides. First experiment result. 30-day recap in public. | Guides indexed; recap posted |

After that: scout → angle → pack → post → measure → learn, every week.

---

## 12. Decisions locked (Oct 1)

- **Crew, keys, and loop:** approved.
- **Planner fields:** added Oct 1 (Scout Score, Hook Type, Subscribers Driven, Link Clicks, Replies, Promenade Clicks, plus X and Blog / SEO as platforms).
- **Morning pick message:** Slack, in a private channel just for this (`#charm-desk`).
- **Your take:** reply in the Slack thread, **or** dictate it with Wispr Flow straight into Claude. If Slack acts up, the "Q's Take" field in Notion works too. Agents check all three.
- **Grok:** trends only, plus one extra job: learn how Baltimore business news travels on X (who breaks it, who amplifies it) and keep a watchlist.
- **Voice file:** Q's `brand-voice.md` goes in `voice/`. (The one in Google Drive is Holmes Hydration's, not Q's.)
- **Instagram/Threads:** convert the Full Court Founder IG (115 followers) to the Charm City Coin handle (TBD). Its Threads profile becomes the Charm City Coin Threads. The Work With Charm Threads (20 followers) posts a "we moved" note and goes quiet.
- **Weekly founder short:** added Oct 1 as the Producer agent.

---

## 13. Where you come in (plain language)

Everything not on this list runs without you.

### Every weekday (about 20-30 minutes total)

| When | What shows up | What you do | Time |
|---|---|---|---|
| ~7:30am | A Slack message in `#charm-desk`: today's top 3 stories, 2-3 angles each, one question per story | Reply with your picks and your take, e.g. *"1B, 3A. On 1: ..."*. Or dictate it to Claude with Wispr Flow. Or skip a day. | 5 min |
| ~10am | A second Slack message: "pack ready" with a Notion link | Read the drafts. Fix anything that doesn't sound like you. | 5-10 min |
| Whenever you post | Paste-ready text for X, Threads, LinkedIn; the carousel slides for IG | **You post them by hand.** Then reply in the thread with the post links. | 5-10 min |

Slack replies aren't instant triggers. The agents check the thread at set times (about 9am, noon, and 3pm). If you need it faster, dictate to Claude directly.

### Every week

| When | What shows up | What you do | Time |
|---|---|---|---|
| Saturday | Slack: the founder short script | Read it, fill in your pick | 5 min |
| Sunday | Your phone | **Record the short:** open, the event rundown, your pick, the CTA. One take is fine. | 10 min |
| Monday | The edited short + captions on the Planner item | Post it on each platform, paste the links back | 10 min |
| Sunday evening | Slack: the scoreboard, 3-5 lessons, proposed changes to how Scout ranks stories, and next week's experiment | Reply "yes," "no," or "yes except #2" | 5 min |
| Sunday evening | Instagram and LinkedIn numbers (until those are connected) | Drop screenshots of IG and LinkedIn insights in the thread. The agents can't read those apps yet. | 5 min |
| Sunday night or Monday morning | Monday "This Week" issue drafted in Beehiiv | Read it, hit **schedule** | 10 min |
| Tuesday-Wednesday | One SEO article draft | Approve, edit, or kill it | 5-10 min |
| Thursday | The Take + the weekly show (from Oct 8) | **This is your feature.** You write or dictate the take and record the show. Agents package it, cut clips, and draft the posts. | Your on-camera time |

### Sometimes

- **Site changes** (SEO pages, Radar hub): I open a pull request, you say "merge."
- **A story is touchy** (names a person, a dispute, unverified): the agent flags it in Slack and waits for you.
- **The Learning Ledger:** it's yours to edit any time. Your edits win.

### Never automatic, always you

Posting to social. Sending the newsletter. Merging site code. Adding anyone to any list.
