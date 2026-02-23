# Position: Integration Tax Is the Real Cost

**Commitment:** Evaluate all tooling platform options (build, buy, unify) primarily on integration cost — not license fees, development speed, or feature checklists. The ~15 integration points between internal tools and product infrastructure are the dominant cost driver and the primary source of migration risk.

**Reasoning:** The Retool evaluation 18 months ago failed not on price or features but on inability to handle custom data pipeline integrations. This pattern will repeat with any vendor: commodity features are easy to match, but the integration surface is unique to our systems. License cost ($200k/yr) is small compared to the engineering time lost to integration problems (estimated at 30% of senior engineer time across 6 disconnected tools). Any cost analysis that focuses on sticker price vs. development cost is asking the wrong question.

**Connections:**
- Foundational to Position 001 — the integration tax argument is why building the core in-house is defensible
- Informed the Round 2 three-option comparison: "unify existing" is attractive precisely because it has the lowest integration disruption
- Part of the month-8 decision criteria (Position 003): a vendor that handles data pipeline integrations natively would change this calculus

**Status:** Resolved

This was a false-tension resolution: the initial "build vs. buy" framing implied the decision was about cost and speed. Reframing around integration cost dissolved the apparent tension — once integration is the primary criterion, the analysis becomes much clearer.
