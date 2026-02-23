# Position: Build Core, Buy Periphery

**Commitment:** Build the core platform (unified auth, data layer, UI shell) in-house using a phased approach. Adopt third-party solutions only for commodity capabilities (e.g., feature flag services) where no custom integration advantage exists. Defer any vendor platform evaluation to month 8, with explicit criteria for triggering it.

**Reasoning:** The core platform is fundamentally an integration layer connecting ~15 internal systems. This integration surface is the dominant cost and risk — it's what killed the Retool evaluation 18 months ago. Building in-house means the integration layer is designed around our actual systems rather than forcing our systems to conform to a vendor's model. The phased approach (unify data tools → auth + UI shell → evaluate) delivers incremental value starting month 4 and preserves optionality through month 8, though we honestly acknowledge the buy offramp is unlikely to be taken unless clear failure criteria are met.

**Connections:**
- Resolves the "build vs. buy" framing by reframing it as "what does the platform team build on?" (Round 1)
- Depends on Position 002 (integration tax) — the integration surface being the dominant cost is what makes in-house build defensible
- Depends on Position 003 (team capacity sequencing) — this only works if Priya + 1 hire can execute the phased plan
- The Round 2 "false tension" (lost time vs. buy path) supports this: the 2-month delay is offset by incremental value delivery

**Status:** Resolved

Evolved across all three rounds:
- Round 1: Identified as "build core, buy periphery"
- Round 2: Refined to phased approach with deferred buy decision
- Round 3: Finalized with acknowledgment that the buy offramp is likely illusory, plus explicit failure criteria at month 8
