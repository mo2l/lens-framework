# The LENS Framework

**Structured sparring with AI to make better decisions.**

For anyone using AI to think through decisions that matter — strategy, architecture, hiring, product direction.

## The Problem

AI conversations about important decisions tend to drift. The AI agrees too easily, blind spots go unchallenged, and you end up with a summary of what you already thought — not sharper thinking.

LENS is structurally different from typical prompt engineering. The AI acts as a **challenger**, not an assistant — it's designed to push back. Perspectives you define persist across the entire session, not just a single exchange. And you end with **committed positions** backed by reasoning, not a chat summary.

## How LENS Works

You define **lenses** — persistent pressure-test perspectives like *"Can we actually staff this?"* or *"What do we stop doing to make room?"*. These aren't throwaway prompts; they stay active throughout the session, ensuring nothing slips through unchallenged.

The AI **challenges** your thinking through those lenses across structured **rounds**. Each round clusters questions, pushes back through relevant lenses, and captures your responses as **positions** — concrete commitments with reasoning, not discussion summaries.

After all rounds complete, a **synthesis** pulls everything together: resolved positions, unresolved items, risks, and conviction shifts.

The human brings domain knowledge and owns every decision. The AI challenges, captures, and surfaces contradictions — it never commits on your behalf.

| Concept | What it means |
|---|---|
| **Lenses** | Persistent pressure-test perspectives that prevent blind spots |
| **Rounds** | Structured cycles: cluster questions, challenge, respond, capture positions |
| **Positions** | Concrete commitments with reasoning — not summaries of discussion |
| **Synthesis** | Final integration after all rounds complete — never mid-session |
| **Emergent Questions** | New questions surfaced during rounds that weren't in the original scope |

> **Example:** You're deciding whether to build or buy a data pipeline. You set lenses like *"What's the true maintenance cost?"* and *"Do we have the team to build this?"*. After two rounds of challenge, you hold a position: *"Build in-house — we accept 2 months longer timeline because our data model is too custom for off-the-shelf. Confidence: high. Risk: team capacity if the auth project slips."* The synthesis captures this alongside unresolved items and conviction shifts from the session.

## Quick Start

### Option A: Any AI chat (no setup)

Works with ChatGPT, Claude, Gemini, Copilot, or any AI:

1. Paste [`prompts/create-scope.md`](prompts/create-scope.md) into any AI chat — it walks you through building your scope interactively
2. Paste [`prompts/run-session.md`](prompts/run-session.md) + your scope into any AI chat — the AI runs the full session

No file system access needed. See [`prompts/README.md`](prompts/README.md) for details.

### Option B: File-based (with AI agent)

1. `cp -r scopes/_template scopes/my-topic`
2. Edit `scopes/my-topic/SCOPE.md` — define your topic, choose 4-8 lenses, map your session arc
3. Point your AI agent at `AGENTS.md` and start

## Project Structure

```
AGENTS.md                    # AI behavioral contract (start here)
README.md                    # This file
prompts/
  create-scope.md            # Guided scope creation — paste into any AI
  run-session.md             # Guided session runner — paste into any AI
  extract-positions.md       # Extract positions from an existing chat
  follow-up.md               # Post-session follow-up review (2-4 weeks later)
docs/
  FRAMEWORK.md               # Complete methodology reference
  USAGE.md                   # Step-by-step guide for AI agents
scopes/
  _template/                 # Copy this to start a new scope
    SCOPE.md                 # Topic, lenses, arc, context
    rounds/                  # Round files (01-definition.md, etc.)
    positions/               # Extracted position files
    synthesis/               # Final synthesis documents
    follow-up/               # Post-session follow-up reviews
```

## Documentation

- **[prompts/](prompts/)** — Copy-paste prompts for any AI. The easiest way to get started.
- **[AGENTS.md](AGENTS.md)** — Entry point for AI agents. Contains the complete behavioral contract.
- **[docs/FRAMEWORK.md](docs/FRAMEWORK.md)** — Full methodology reference: roles, round structure, lenses, position formation, session arc.
- **[docs/USAGE.md](docs/USAGE.md)** — Step-by-step guide with examples for running a LENS session.
- **[docs/GLOSSARY.md](docs/GLOSSARY.md)** — Glossary of all LENS-specific terminology.

## License

This work is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).
