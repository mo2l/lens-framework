# Round 1: Definition

## Lenses Applied
- **Total Cost of Ownership** — Applied to challenge whether "build" and "buy" costs are being compared honestly
- **Scaling Readiness** — Applied to test whether the definition accounts for the 40→80 person growth
- **Integration Complexity** (secondary) — Applied because the definition of "platform" hinges on how many integration points exist

## Clustered Questions

### Cluster A: What counts as "the platform"?
- Which of the 6 existing tools are actually platform-level vs. team-specific utilities?
- What's the minimum viable scope — everything unified, or just the shared pain points (auth, data pipelines)?

### Cluster B: What does "buy" actually mean here?
- Are we talking about replacing everything with one vendor, or buying components and integrating them?
- Given the Retool rejection, has the vendor landscape changed enough to revisit?

## Challenges & Responses

**AI Challenge (Total Cost of Ownership):** You're framing this as "build vs. buy" but your current state is already "built" — you have 6 tools. The real question might be "unify what we have vs. replace with something purchased." Those have very different cost profiles. Which are you actually deciding?

**Human Response:** Fair point. We're not starting from zero. Three of the six tools are basically wrappers around the same data — the deploy dashboard, the incident tracker, and the metrics viewer all pull from the same pipeline but have separate UIs and auth. The other three (feature flags, config management, experiment platform) are genuinely separate. So "the platform" is probably: unified auth + unified data layer + shared UI shell. The three data tools merge into that shell. The three independent tools stay independent but get shared auth.

**AI Challenge (Scaling Readiness):** That scoping is pragmatic, but test it against the 80-person future. Right now senior engineers maintain these tools as a side job. At 80 people, is "shared auth + data layer + UI shell" enough, or will you need a dedicated platform team regardless of build/buy? If you need a platform team either way, the build/buy question changes — it becomes "what does the platform team build on?"

**Human Response:** That's a good reframe. We probably do need a platform team at 80 people no matter what. So the real question is: does that team spend its first year building infrastructure from scratch, or do they start with a purchased foundation and customize on top?

> **AI Influence Note:** I'm steering this toward a "buy the foundation, build on top" framing. That might be the right answer, but I want to flag that I've narrowed the option space. The "invest heavily in unifying what we already have" path might be cheaper if the existing tools are closer to good than you think. Push back if that's worth exploring.

**Human Response:** Noted. The existing tools actually aren't that far off — the three data tools share a pipeline already. The gap is really auth and UI, not core functionality. So "unify existing" is genuinely a third option. Let's keep all three on the table.

**AI Challenge (Integration Complexity):** How many integration points exist between these 6 tools and your product infrastructure? Every integration is a migration cost for "buy" and a maintenance cost for "build." Do you have a rough count?

**Human Response:** Rough estimate: 12-15 integration points. The data pipeline tools connect to our deployment system, monitoring, and the data warehouse. Feature flags integrate with the CI/CD pipeline and the experiment platform. Config management touches everything. The integration surface is bigger than people think, which is partly why the Retool evaluation failed — they couldn't handle our custom data pipeline integrations.

## Positions Captured

- **Position 001: Build core, buy periphery** → `positions/001-build-core-buy-periphery.md`
  The platform is: unified auth + data layer + UI shell. Build this in-house because it's the integration layer that connects to 12-15 internal systems. Buy/adopt components where they're commodity (e.g., feature flag service) rather than building those from scratch.

- **Position 002: Integration tax is the real cost** → `positions/002-integration-tax.md`
  The integration surface (~15 points) is the dominant cost driver. Any solution — build or buy — must be evaluated primarily on integration cost, not license fees or development speed.

## Emergent Questions
- "What does the platform team's first year look like under each option?" → routed to Round 2
- "If we buy a foundation, what's the switching cost if it doesn't work out?" → routed to Round 3
- "Who maintains the three independent tools (feature flags, config, experiments) long-term?" → routed to Round 2

## Status

| Topic | Status | Notes |
|---|---|---|
| Platform scope definition | Resolved | Unified auth + data layer + UI shell; three data tools merge, three stay independent with shared auth |
| Build vs. buy framing | Resolved | Reframed as "what does the future platform team build on?" — three options: build from scratch, buy foundation + customize, unify existing |
| Integration complexity as cost driver | Resolved | ~15 integration points; this is the dominant evaluation criterion |
| "Unify existing" as third option | Carry forward | → Round 2: needs cost/capacity analysis alongside build and buy |
