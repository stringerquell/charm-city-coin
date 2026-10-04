# The product: Charm City Coin Promenade (b2b-baltimore repo)

> Repo: https://github.com/stringerquell/b2b-baltimore (private) · Test build: https://b2b-baltimore.vercel.app
> This file describes the product so media agents know where to send people. Code changes happen in that repo, never here.

## What it is
A strollable, voxel-style Inner Harbor promenade where Baltimore B2B service providers claim and build digital storefronts. In the strategy it is **the showroom and the bottom of the funnel**, not the headline. Media earns attention; the Promenade is where readers see the network and providers claim a seat.

## Pages agents can link to
| Path | What it is | Use it when |
|---|---|---|
| `/` | The city (3D promenade) | "Walk the city" links, newsletter footer |
| `/plot/[n]` | A single storefront, e.g. `/plot/1` (Quickship Studio) | A story mentions a member |
| `/directory` | Plain list of providers by category | Fallback link, accessibility |
| `/claim` (planned) | Claim flow with the founding pitch | Provider-facing posts, once the offer is written |

Always add UTM tags (see `templates/utm-convention.md`).

## Rules that come from the strategy
- **Public data never becomes buildings.** Filings, permits, and awards go in the newsletter and the Radar, not into the city as unclaimed storefronts.
- **Blocks of 10, one of each trade per block.** Show Block 01 plus a few free editorial landmarks.
- **Editorial landmarks** (e.g. the Reginald F. Lewis Museum) can link to our coverage. They are clearly unpaid and imply no endorsement of nearby members.
- **Sponsors get landmarks, never block seats.**
- **No simulated numbers in public.** The test build has simulated visitor/view counts; don't cite them.
- Quickship Studio (Plot 01) is Q's company; disclose that whenever it appears in coverage.

## Current state (Oct 1, 2026)
- Quickship Studio is the one real business; the others are fictional samples.
- Storefronts people build are saved only in their own browser. Accounts, payments, and a shared database come later.
- Stack: Next.js, React, three.js, deployed on Vercel.
