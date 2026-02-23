# Round 3: Risks

## Lenses Applied
- **Scaling Readiness** — Stress-testing whether the phased plan from Round 2 actually works at 80 people
- **Optionality** — Testing whether the "defer buy decision" is genuine optionality or just procrastination
- **Team Capacity** (secondary) — Revisiting key-person risk from Round 2
- **Total Cost of Ownership** (secondary) — Pressure-testing the Phase 3 decision criteria

## Clustered Questions

### Cluster A: Is the phased plan robust?
- From Round 2 emergent: "Is the phased approach actually three small bets or one big bet disguised as phases?"
- From Round 2 emergent: "What happens if Priya leaves during Phase 1?"
- Does the phased plan survive contact with the hiring timeline?

### Cluster B: The month-8 decision
- From Round 2 emergent: "What are the criteria at month 8 for choosing build-continued vs. buy-foundation?"
- From Round 1 emergent: "If we buy a foundation, what's the switching cost if it doesn't work out?"

## Challenges & Responses

**AI Challenge (Optionality):** Round 2 framed Phase 3 as "genuine optionality." But is it? By month 8, you'll have 8 months of custom-built auth and UI shell. The switching cost to a vendor platform at that point isn't zero — you'd be throwing away Phase 2's work. Are you actually deferring the decision or have you already made it by building?

**Human Response:** That's a real concern. If Phase 2 produces a working auth system and UI shell, there's strong path dependency — nobody will want to rip that out for a vendor solution. The "decision at month 8" might be illusory. Honestly, the phased approach is probably a "build" decision with an offramp we'll never take.

**AI Challenge (Scaling Readiness):** Accept that for a moment — you're effectively choosing "build." Does a 2-person platform team (Priya + 1 hire) sustain a custom platform for 80 engineers? At some point, the platform itself needs a roadmap, support rotation, documentation, and on-call. What's the steady-state team size, and when does it need to grow?

**Human Response:** Good point. At 80 engineers, a platform serving everyone probably needs 3-4 people — Priya's team would need to grow by month 12-14. That's a hiring dependency we haven't planned for. But the alternative — a vendor platform — also needs 1-2 people managing it. The delta is 1-2 additional heads, not 3-4 vs. zero.

**AI Challenge (Team Capacity):** Key-person risk: Priya is the lynchpin of Phase 1 and 2. She has context on the data pipeline tools that nobody else has. What happens if she leaves at month 3? Is this a "the project stalls for 6 months" scenario or a "someone else picks it up with a 2-month delay" scenario?

**Human Response:** Honestly, if Priya leaves mid-Phase 1, it's probably a 4-month setback. She has undocumented knowledge about the data pipeline integrations. We should front-load documentation in Phase 1 — first two weeks should be Priya documenting the integration map before writing any new code. That way the knowledge is captured even if she leaves.

**AI Challenge (Total Cost of Ownership):** Let's define the month-8 decision criteria concretely. What would have to be true for you to choose "buy a vendor platform" at month 8 instead of continuing to build?

**Human Response:** Three things: (1) Phase 1+2 are significantly behind schedule — like, auth isn't working by month 8; (2) a vendor has appeared that handles our data pipeline integrations natively — this was the Retool blocker; (3) the platform team can't hire a third person, meaning we're capacity-constrained on build. If none of those are true, we continue building. If two or more are true, we seriously evaluate vendors.

**AI Challenge (Scaling Readiness):** One more risk. You're doubling the team over 12 months. The phased plan delivers the unified data tools by month 4 and full platform by month 8. But hiring is front-loaded — you might have 60 people by month 6. That means 20 new engineers onboarding onto the old broken system before Phase 1 delivers. Is that acceptable or do you need an interim fix?

**Human Response:** We need an interim fix. A lightweight onboarding guide and some scripts to automate the worst of the multi-tool setup. Two days of work, not a project. Good catch — I would have missed that without the scaling lens.

## Positions Captured

- **Position 001 (finalized):** "Build core, buy periphery" is now effectively "build with an honest assessment that the buy offramp is unlikely." The phased plan is a build commitment with defined failure criteria at month 8 that would trigger a vendor evaluation.

- **Position 003 (refined):** Team capacity sequencing now includes: front-load documentation in first 2 weeks of Phase 1, plan for platform team growth to 3-4 by month 14, create interim onboarding fix before Phase 1 delivers.

## Inversion Challenge

**AI (Inversion):** The emerging consensus across all three rounds is "build." Let me construct the strongest case for "buy":

*Assume the answer is "buy a vendor platform." The best path: adopt a platform like Retool or Backstage, accept the integration pain upfront (3-month migration), and redirect Priya's team to building only the custom data pipeline connectors as plugins. You avoid the 3-4 person steady-state platform team entirely, you get vendor-maintained auth/UI/hosting, and you trade control for speed. The integration surface — your main objection — is a solvable engineering problem, not an architectural blocker. Retool failed 18 months ago, but the product has changed. What breaks about this path?*

**Human Response:** Two things break it. First, "the product has changed" is speculative — we'd need to re-evaluate Retool specifically, and that's a month of work before we even start. Second, the integration surface isn't just technical — it's the data pipeline auth tokens, the custom monitoring hooks, the deployment scripts. Those are deeply coupled to our infrastructure. A vendor platform would need a shim layer that we'd still have to build and maintain. So we'd end up with vendor platform + custom shim layer + vendor lock-in. The build path gives us full control over the integration surface, which is where all the complexity actually lives.

But — I'll grant that we should formally re-evaluate Retool at month 8 as part of the decision criteria. If they've genuinely solved the integration surface problem, that changes the calculus.

**Position captured:** Month-8 vendor evaluation should include a specific Retool re-assessment focused on integration surface capabilities. Added to decision criteria.

## Emergent Questions
- "Should we formalize the month-8 review as a scheduled decision meeting with stakeholders?" (operational — beyond scope, noted for implementation)
- "How do we handle the political sensitivity of 'replacing' tools that teams built?" (noted but not addressed in this scope — could be a separate LENS session on change management)

## Status

| Topic | Status | Notes |
|---|---|---|
| Phase 3 optionality | Resolved | Acknowledged as likely illusory — the phased approach is effectively a build decision with explicit failure criteria for reconsidering |
| Steady-state platform team size | Resolved | 3-4 people by month 14; delta vs. vendor-managed is 1-2 additional heads |
| Key-person risk (Priya) | Resolved | Mitigated by front-loading documentation in first 2 weeks of Phase 1 |
| Month-8 decision criteria | Resolved | Three criteria: (1) significantly behind schedule, (2) vendor handles data pipeline natively, (3) can't hire third platform engineer. Two of three triggers vendor evaluation |
| Interim onboarding fix | Resolved | Lightweight guide + automation scripts; ~2 days of work before Phase 1 delivers |
| Political sensitivity of replacing team-built tools | Unresolved | Real risk, acknowledged but out of scope. Recommended as separate LENS session on change management |
