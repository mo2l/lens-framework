# Scope: Build vs. Buy Internal Tooling Platform

## Topic

Should we build a custom internal tooling platform or buy/adopt an existing solution? We're a 40-person product engineering org spending ~30% of senior engineer time on internal tools that have grown organically. The tools work but don't compose, onboarding is painful, and we're about to double the team.

## Context

- Current stack: 6 disconnected internal tools built by different teams over 3 years
- Pain points: no shared auth, no unified UI, duplicated data pipelines, 2-week onboarding overhead
- Budget: could afford a mid-tier platform license (~$200k/yr) or 2 FTEs dedicated to internal tooling
- Timeline pressure: hiring plan doubles eng team in 12 months — current tools won't scale
- Political reality: the teams that built existing tools have ownership pride; "replacing" their work is sensitive
- Prior attempt: evaluated Retool 18 months ago, rejected for lack of flexibility on data pipeline tooling

## Lenses

| # | Lens | Forcing Question |
|---|---|---|
| 1 | Total Cost of Ownership | "What does this actually cost over 3 years — including hidden costs like integration, migration, and lost productivity?" |
| 2 | Team Capacity | "Can we actually staff this without starving product work — and what doesn't get built if we do?" |
| 3 | Integration Complexity | "How many systems need to talk to each other, and what breaks when they don't?" |
| 4 | Scaling Readiness | "Does this still work when the team is 80 people instead of 40?" |
| 5 | Optionality | "Does this decision lock us in or keep future options open?" |

## Session Arc

```
Round 1: Definition — What does "internal tooling platform" actually mean for us?
Round 2: Tradeoffs — What are the real costs, constraints, and second-order effects?
Round 3: Risks — What breaks, what's unresolved, and what are we assuming?
```

## Lens Coverage

| Round | Primary Lenses (always apply) | Secondary Lenses (if relevant) |
|---|---|---|
| Round 1 | Total Cost of Ownership, Scaling Readiness | Integration Complexity |
| Round 2 | Team Capacity, Integration Complexity, Optionality | Total Cost of Ownership |
| Round 3 | Scaling Readiness, Optionality | Team Capacity, Total Cost of Ownership |

## Human Experience Level

- [x] **Moderate** — I know the space but have gaps; help me articulate what I know vs. assume
