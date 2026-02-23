# LENS Framework — Usage Guide

Step-by-step instructions for running a LENS session with any AI agent.

---

## 1. Create a Scope

```bash
cp -r scopes/_template scopes/my-topic
```

## 2. Configure SCOPE.md

Edit `scopes/my-topic/SCOPE.md` with:

- **Topic:** The decision or challenge to explore
- **Lenses:** 4-8 pressure-test perspectives specific to your domain
- **Arc:** The round sequence (default: Definition → Internal → External → Adoption → Risks)
- **Context:** Background information the AI needs to challenge effectively

## 3. Start the Session

Point your AI agent at `AGENTS.md`:

> "Read AGENTS.md and then begin a LENS session using scopes/my-topic/SCOPE.md."

The agent will:
1. Read `AGENTS.md` for behavioral rules
2. Read `scopes/my-topic/SCOPE.md` for session configuration
3. Begin Round 1 with clustered challenges through the defined lenses

## 4. Work Through Rounds

For each round:

1. **AI clusters questions** by theme and opens with lens-driven challenges
2. **You respond** with your perspective, experience, and judgment
3. **AI captures positions** — concrete commitments, not summaries — and notes emergent questions
4. **AI checks for reopens** — does any new insight contradict or reframe a position from a prior round? If so, flag it for re-examination
5. **Round closes** with explicit status on every topic (Resolved / Unresolved / Carry forward)

After each round, ask the AI to save the round file:

> "Save this round to rounds/01-definition.md"

And extract positions:

> "Extract the positions from this round into the positions/ directory."

## 5. Between Rounds

Review captured positions and emergent questions before starting the next round. The AI should reference prior positions when opening challenges in later rounds.

## 6. Synthesis

After all rounds are complete:

> "We've completed all rounds. Synthesize the positions into a final document in synthesis/."

The AI will:
- Gather all positions from `positions/`
- Cross-reference for contradictions
- Conduct an **Inversion Challenge** in the final round — arguing the strongest case against the emerging consensus before synthesis
- Produce a structured synthesis document including Conviction Shifts (what the human's thinking changed on)

**Never ask for synthesis mid-session.** Complete all rounds first.

## 7. Resuming a Session

If you need to continue a session in a new conversation, point the AI at the scope:

> "Read AGENTS.md, then read all files in scopes/my-topic/ to resume this LENS session."

The round files and positions provide full context to continue where you left off.

## 8. Follow-Up Review

2-4 weeks after completing a session, revisit the decisions using the follow-up prompt:

> "Read `prompts/follow-up.md` and review the session in `scopes/my-topic/`."

The AI will:
- Review all positions and unresolved items
- Check which decisions have been acted on, which are stalled, and which need revision
- Produce a follow-up document saved to `follow-up/` in the scope directory

---

## Example: Designing a Lens Set

For a **product launch** decision:

| # | Lens | Forcing Question |
|---|---|---|
| 1 | Market Readiness | "Is the market actually ready for this, or are we projecting?" |
| 2 | Resource Reality | "Can we ship this with current team and budget?" |
| 3 | What Stops | "What do we stop doing to make room for this?" |
| 4 | Customer Impact | "Does the target customer's life measurably improve?" |
| 5 | Competitive Response | "What does the competitor do when they see this?" |
| 6 | Failure Mode | "How does this fail, and can we recover?" |

## Example: Custom Session Arc

Not every topic needs the default 5-round arc. Adapt to your context:

**3-round arc** for a focused technical decision:
```
Round 1: Definition — What problem are we actually solving?
Round 2: Tradeoffs — What do we gain and lose with each approach?
Round 3: Risks — What breaks, and what's our fallback?
```

**6-round arc** for a complex organizational change:
```
Round 1: Definition — What does this change actually mean?
Round 2: Current State — What's really happening today?
Round 3: Target State — What does success look like?
Round 4: Path — How do we get from here to there?
Round 5: People — How do individuals and teams adapt?
Round 6: Risks — What can go wrong, what's unresolved?
```
