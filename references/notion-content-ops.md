# Charm City Coin Content Ops (snapshot)

> **Brand renamed Oct 4, 2026:** "Charm City B2B" in this copy now reads "Charm City Coin".
> **Snapshot taken Oct 1, 2026** from Notion: https://app.notion.com/p/3e96d307028981b9b1e7c080bee9a95b
> Notion wins if they disagree.

Home base for Charm City Coin content: every post and every newsletter issue lives here. Strategy lives in the Charm City Coin Strategy Doc.

## How it works
1. **Scout** drops daily Baltimore items into the Content Planner as 💡 Idea, with source links.
2. **Chief** adds 2–3 angles; status moves to 🎯 Angles.
3. **Q picks** an angle (voice note). Status: ✍️ Drafting.
4. **Writers** draft per platform and run the voice gate. Status: 👀 Ready for Q.
5. **Q approves and posts by hand.** Status: 🚀 Published. Add the posted URL and numbers.

**Newsletter:** each issue is a page in Newsletter Issues. Content Planner items tagged with a newsletter section link to the issue they run in. Evergreen items (takes, recaps, reviews) can be batched; time-sensitive items (events, news) get filled the day before the send.

**Cadence:** Monday = This Week (events + buzz). Thursday = The Take (Q's feature). Weekly for the first two weeks, then twice weekly.

## Newsletter format (modeled on The Rundown)
- **Open:** "Good morning, Baltimore" + two lines setting up the issue + welcome to new readers.
- **In this issue:** 3–4 bullet table of contents.
- **Each story:** section label (e.g., THE TAKE, THIS WEEK, BUZZ) → headline linking the source → **The rundown** (2–3 sentences) → **The details** (3–4 bullets) → **Why it matters** (what it means for a Baltimore operator).
- **Sponsor slot:** "Presented by" block formatted like a story, clearly labeled.
- **Quick hits:** one-line Baltimore business items with links.
- **Sign-off:** from Q, with a line on what's coming next issue.

## Databases
- **Newsletter Issues:** https://app.notion.com/p/eea656e8dbac417ba09d8e6abde737bd (data source `collection://78ac7f32-12e0-42a7-a966-c631631eb9d6`)
- **Charm Content Planner:** https://app.notion.com/p/da85dfd7ec8c424d819f47d354048f78 (data source `collection://47b37859-d789-46c0-a71f-d3048403c622`)

### Content Planner fields (as of Oct 1, 2026)
| Field | Type | Values |
|---|---|---|
| Title | title | |
| Status | select | 💡 Idea, 🎯 Angles, ✍️ Drafting, 👀 Ready for Q, ✅ Scheduled, 🚀 Published, ⏭️ Skipped |
| Lane | select | Events & Networking, Business Now, Q's Take, Where to Work, Behind the Business, Baltimore History, Launch |
| Platform | multi-select | Threads, Instagram, LinkedIn, Newsletter, X, Blog / SEO |
| Format | select | Text post, Carousel, Reel / Short, Image, Newsletter section |
| Newsletter Section | select | The Take, This Week, Buzz, Quick Hits |
| Newsletter Issue | relation | → Newsletter Issues |
| Timing | select | Evergreen (batchable), Time-sensitive |
| CTA | select | Subscribe, Get the Outlook, Comment keyword, Waitlist, None |
| Hook Type | select | Number, Name, Question, Contrarian, Story, List |
| Source / Source Name | url / text | |
| Angle, Hook, Q's Take, Businesses Tagged | text | |
| Publish Date | date | |
| Posted URL | url | |
| Scout Score | number | 0-100 from the scoring rubric |
| Views, Saves, Shares, Follows Gained, Replies, Link Clicks, Subscribers Driven, Promenade Clicks | number | Filled after posting |

Related page: "Money on the Move — Research Brief (second agent)": https://app.notion.com/p/3e96d307028981c98584ece66206a967
