# Synthesis: Build vs. Buy Internal Tooling Platform

## Decision Summary

**We are building the core internal tooling platform in-house using a phased approach, with an explicit (but likely unused) offramp to vendor evaluation at month 8.**

The decision was driven by one key insight: the integration surface (~15 points connecting 6 internal tools to product infrastructure) is the dominant cost driver. This makes in-house building defensible because we're building an integration layer around our specific systems, not a generic platform.

---

## Resolved Positions

### 1. Build Core, Buy Periphery → `positions/001-build-core-buy-periphery.md`
Build unified auth + data layer + UI shell in-house. Adopt vendor solutions only for commodity capabilities. The "buy" option remains formally available at month 8 but is acknowledged as unlikely unless explicit failure criteria are met.

**Evolved across all 3 rounds:** Started as "build vs. buy," reframed as "what does the platform team build on," finalized as a phased build commitment with honest acknowledgment of path dependency.

### 2. Integration Tax Is the Real Cost → `positions/002-integration-tax.md`
All options evaluated primarily on integration cost, not license fees or development speed. The Retool failure 18 months ago validates this: vendor solutions fail at the integration surface, not on features.

**False tension resolved:** The "build vs. buy" framing implied a cost/speed tradeoff. Once integration was identified as the primary criterion, the apparent tension dissolved.

### 3. Team Capacity Sequencing → `positions/003-team-capacity-sequencing.md`
Platform team seeded with Priya (internal) + 1 external hire. Phased delivery: unify data tools (months 1-4) → auth + UI shell (months 5-8) → evaluate and grow (month 8+). Documentation front-loaded. Interim onboarding fix before Phase 1 delivers.

---

## Unresolved Items

| Item | Why Unresolved | Resolution Criteria | Target |
|---|---|---|---|
| Platform team growth to 3-4 | No headcount approval or hiring plan | Leadership approves headcount; job description written for hire #3 | Month 6 |
| Political sensitivity of replacing team-built tools | Acknowledged as real risk, deliberately scoped out | Requires change management conversation — potentially its own LENS session | No date set |

---

## Month-8 Decision Criteria

At month 8, evaluate whether to continue building or pivot to a vendor platform. Trigger a vendor evaluation if **two or more** of these are true:

1. Phase 1+2 are significantly behind schedule (auth not working by month 8)
2. A vendor has emerged that handles custom data pipeline integrations natively
3. The platform team cannot hire a third engineer (capacity-constrained on build)

---

## Key Risks

| Risk | Severity | Mitigation |
|---|---|---|
| Key-person dependency on Priya | High | Front-load documentation in first 2 weeks of Phase 1 |
| 20 new engineers onboarding before Phase 1 delivers (month 4-6 gap) | Medium | Interim onboarding guide + automation scripts (~2 days of work) |
| Phased plan is actually an irreversible build commitment | Medium | Accepted — month-8 criteria formalize this, but the offramp is honestly unlikely |
| Platform team undersized at 80 people | Medium | Plan growth to 3-4 by month 14; delta vs. vendor-managed is only 1-2 additional heads |

---

## Cross-Reference Map

```
Position 001 (Build Core)
  ├── depends on → Position 002 (Integration Tax) — integration surface justifies in-house build
  ├── depends on → Position 003 (Sequencing) — phased plan is the execution mechanism
  └── informed by → Round 1 reframing, Round 2 option comparison, Round 3 optionality challenge

Position 002 (Integration Tax)
  ├── informs → Position 001 — primary argument for build over buy
  ├── informs → Month-8 criteria — criterion #2 (vendor handles integrations) would change this calculus
  └── resolved → False tension from original "build vs. buy" cost framing

Position 003 (Sequencing)
  ├── enables → Position 001 — without staffing plan, the build doesn't happen
  ├── partially unresolved → Team growth and political sensitivity
  └── informed by → Round 2 capacity analysis, Round 3 key-person and scaling risks
```

---

## AI Influence Log

One notable moment of AI framing influence occurred in Round 1: the AI steered the conversation toward a "buy the foundation, build on top" framing, which was flagged transparently. The human pushed back and reintroduced "unify existing" as a third option — which ultimately became Phase 1 of the final plan. The influence was caught and corrected because it was named.

---

## Conviction Shifts

Entered believing build-vs-buy was the real question; exited seeing it as an integration surface question. The framing shift happened in Round 1 when the AI challenged "what are you actually deciding?" — the answer wasn't "build or buy" but "who owns the integration surface." Once that reframe landed, "build" became almost inevitable because the integration surface is where all the complexity lives, and outsourcing complexity ownership to a vendor doesn't reduce it.

Also entered assuming the phased plan preserved genuine optionality. Exited acknowledging the path dependency honestly — the month-8 "decision point" is really a checkpoint, not a fork. That honesty was uncomfortable but more useful than pretending we hadn't already committed.

---

## What This Scope Did Not Address

- Change management for teams whose tools are being "replaced" (recommended as separate LENS session)
- Specific vendor evaluation for commodity components (feature flags, etc.)
- Detailed technical architecture of the unified platform
- Budget approval process for the platform team headcount
