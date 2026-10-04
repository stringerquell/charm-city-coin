# Scout scoring rubric

Scout scores every item 0-100 by adding the weights below, capped at 100. **These are starting weights (my best guess, Oct 1).** The Analyst proposes changes every Sunday, max ±5 per factor per week, and the current numbers always live in the Learning Ledger. If the Ledger and this file disagree, the Ledger wins.

## Positive factors

| Factor | Default weight | Counts when |
|---|---|---|
| `has_dollar_figure` | 10 | A real amount from the source (contract, raise, budget, price) |
| `named_business` | 10 | A specific Baltimore business is named |
| `ground_level` | 10 | The business is small or owner-run (roughly under 20 people) |
| `primary_source` | 10 | Link goes to the record or press release, not a write-up of it |
| `fresh` | 10 | Happened or published in the last 48 hours |
| `named_neighborhood` | 5 | A specific neighborhood or corridor |
| `sell_into` | 10 | An owner could act on it: bid, apply, attend, pitch, partner |
| `market_first_fit` | 10 | It's a clean example of winning customers (or of the permission-first order) |
| `lane_need` | 5 | Fills a lane that's light this week |
| `listener_match` | 10 | Matches a question or search from the Listener's report |
| `visual` | 5 | Has a place, person, or number that makes a good carousel or clip |
| `trend` | 5 | Grok flagged it as trending in Baltimore |

## Negative factors

| Factor | Default weight | Counts when |
|---|---|---|
| `unverified` | -20 | Only one secondary source, no primary record |
| `paywall_only` | -10 | Only exists behind a paywall so far |
| `stale` | -10 | Older than 7 days with no new development |
| `national_no_local` | -15 | National story with no specific Baltimore angle |
| `institution_as_villain` | -15 | The only angle is attacking a specific program or agency |

## Lane mix guardrails (applied after scoring)
- At least 2 lanes in the top 10.
- At least 1 ground-level item in the top 10 when one exists.
- No more than 3 items from the same source.
