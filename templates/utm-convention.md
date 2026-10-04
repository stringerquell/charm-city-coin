# Link tagging (UTM) convention

Every link we post gets tags so the Analyst can tell which story sent which subscriber. Writers add these automatically. You don't need to type them.

```
?utm_source={platform}&utm_medium={medium}&utm_campaign={campaign}&utm_content={item}
```

| Part | Values |
|---|---|
| `utm_source` | `x`, `threads`, `instagram`, `linkedin`, `newsletter`, `blog`, `show` |
| `utm_medium` | `social`, `email`, `seo`, `video`, `reply` (for Listener reply opportunities) |
| `utm_campaign` | Week tag + lane, e.g. `w41-businessnow`, `w41-radar`, `launch-oct` |
| `utm_content` | Short slug of the Planner item, e.g. `boe-contract-remington` |

**Examples**
- X thread to the newsletter: `?utm_source=x&utm_medium=social&utm_campaign=w41-businessnow&utm_content=boe-contract-remington`
- Newsletter to a member plot: `/plot/1?utm_source=newsletter&utm_medium=email&utm_campaign=w41-take&utm_content=member-spotlight`
- Radar article to signup: `?utm_source=blog&utm_medium=seo&utm_campaign=w41-radar&utm_content=signup-box`

**Week tag:** ISO week number (Oct 1, 2026 is in week 40).

Beehiiv records `utm_source` / `utm_campaign` on each new subscriber, which is how "Subscribers driven" gets filled per post.
