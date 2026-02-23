# Round 2: Tradeoffs

## Lenses Applied
- **Team Capacity** — Applied to test whether any option is staffable without killing product velocity
- **Integration Complexity** — Applied to compare integration cost across the three options from Round 1
- **Optionality** — Applied to evaluate lock-in and reversibility of each path
- **Total Cost of Ownership** (secondary) — Applied because capacity and cost are inseparable here

## Clustered Questions

### Cluster A: Capacity and sequencing
- From Round 1 emergent: "What does the platform team's first year look like under each option?"
- From Round 1 emergent: "Who maintains the three independent tools long-term?"
- Can we sequence this to avoid a big-bang migration?

### Cluster B: Option comparison
- From Round 1 carry-forward: "Unify existing" needs cost/capacity analysis alongside build and buy
- What do we actually give up under each option?

## Challenges & Responses

**AI Challenge (Team Capacity):** Round 1 established you need a platform team at 80 people regardless. But you're at 40 now and hiring. Where do the platform team members come from? If you pull 2 senior engineers from product teams to seed the platform team, that's ~10% of your current senior capacity gone during a scaling phase. Which product work doesn't happen?

**Human Response:** Realistically, we'd promote one senior engineer who's already doing most of the tools maintenance (Priya — she basically owns the data pipeline tools) and hire one externally. So it's 1 internal move, not 2. Product impact is that Priya's current team loses their most senior member, but she's been asking for this role anyway. The external hire takes 3-4 months to find and onboard.

**AI Challenge (Integration Complexity):** Let's make the three options concrete on integration cost. "Unify existing" touches the 3 data tools' integrations (~8 of the 15 points) but leaves the other 7 alone. "Buy foundation" requires migrating all 15 integration points to the vendor's paradigm. "Build from scratch" is somewhere in between — you rebuild integrations but on your own terms. Is "unify existing" actually the lowest-risk path on integration alone?

**Human Response:** On integration risk, yes — unifying existing is clearly lowest because we're not touching working integrations, just wrapping them. But it doesn't solve the auth problem for the independent tools, and it doesn't give us the UI shell. So it's lowest integration risk but also lowest payoff. The real question is whether "buy foundation" can handle our custom data pipeline integrations — that's what killed Retool.

**AI Challenge (Optionality):** Here's a sequencing question. What if the path is: Phase 1 (months 1-4) — unify the three data tools (low risk, immediate value, Priya leads). Phase 2 (months 5-8) — build shared auth and UI shell on top of that unified base. Phase 3 (months 9-12) — evaluate whether to buy a platform foundation for the next layer or keep building. This preserves optionality because Phase 3 is a decision point with real data, not a bet made today.

**Human Response:** I like the sequencing. It means we're not making the build-vs-buy decision now — we're making it in 8 months with much better information. Phase 1 is almost zero risk because Priya's been wanting to do this anyway. Phase 2 is real work but scoped. The only risk is that we're 8 months in and the "buy" option would have been faster if we'd committed early.

**AI Challenge (Total Cost of Ownership):** Let's pressure-test the "lost time" risk. If a vendor platform takes 6 months to implement (migration + integration), and Phase 1+2 of the build path takes 8 months but delivers incremental value along the way, the time difference is 2 months — but the build path has working improvements from month 4 onward. Is 2 months of delay actually a meaningful cost here?

**Human Response:** No, it's not. The team doubles over 12 months, not overnight. Having the unified data tools by month 4 solves the most acute onboarding pain immediately. The shared auth and UI shell by month 8 handles the next wave. We don't need everything by month 1.

## Positions Captured

- **Position 003: Team capacity sequencing** → `positions/003-team-capacity-sequencing.md`
  Seed the platform team with 1 internal promotion (Priya) + 1 external hire. Sequence work to minimize product team disruption. Defer the full build-vs-buy decision to month 8 when real data exists.

- **Position 001 (refined):** The "build core, buy periphery" position from Round 1 evolves — it's now "phase the build, defer the buy decision." Core infrastructure (auth, data layer, UI shell) is built incrementally. Buying is a future option evaluated with data, not a current commitment.

## Emergent Questions
- "What are the criteria at month 8 for choosing build-continued vs. buy-foundation?" → routed to Round 3
- "What happens if Priya leaves during Phase 1?" → routed to Round 3
- "Is the phased approach actually three small bets or one big bet disguised as phases?" → routed to Round 3

## Status

| Topic | Status | Notes |
|---|---|---|
| Platform team staffing | Resolved | 1 internal (Priya) + 1 external hire; ~5% senior capacity impact, not 10% |
| Three-option comparison | Resolved | "Unify existing" is Phase 1; "build" is Phase 2; "buy" is deferred to Phase 3 decision point at month 8 |
| Sequencing approach | Resolved | Phase 1 (unify data tools, months 1-4) → Phase 2 (auth + UI shell, months 5-8) → Phase 3 (evaluate buy, month 8+) |
| Lost time risk of phased approach | Resolved | False tension — the 2-month delay vs. buy is offset by incremental value delivery starting month 4 |
| Month 8 decision criteria | Carry forward | → Round 3: what would make us choose "buy" at that point? |
| Key-person risk (Priya) | Carry forward | → Round 3 |
