# LENS Guided Prompts

Two self-contained prompts that any AI can follow to run a LENS session. No setup, no plugins — just copy-paste into any AI chat.

## The Prompts

### [`create-scope.md`](create-scope.md) — Create a Scope

Guides you step-by-step through building a SCOPE.md file. The AI asks questions one at a time and assembles the complete scope at the end.

**How to use:**
1. Copy the contents of `create-scope.md` into any AI chat (ChatGPT, Claude, Gemini, Copilot, etc.)
2. Follow the guided conversation — the AI walks you through topic, context, lenses, session arc, and more
3. Save the output as `SCOPE.md`

### [`extract-positions.md`](extract-positions.md) — Extract Positions from a Chat

Extracts structured LENS positions from an existing conversation transcript. Use this when a discussion happened outside of LENS and you want to capture its decisions retroactively.

**How to use:**
1. Copy the contents of `extract-positions.md` into any AI chat
2. Paste your conversation transcript
3. Review the extracted positions and unresolved items
4. Revise until accurate

### [`follow-up.md`](follow-up.md) — Session Follow-Up Review

A lightweight review template to revisit a completed LENS session 2-4 weeks later. Checks on unresolved items and whether resolved positions still hold.

**How to use:**
1. Copy the contents of `follow-up.md` into any AI chat
2. Paste your synthesis document from a past session
3. Walk through each unresolved item and key position
4. Save the updated status table to the scope's `follow-up/` directory

### [`run-session.md`](run-session.md) — Run a Session

Contains everything the AI needs to run a complete LENS session: the behavioral contract, round protocol, position format, synthesis phase, and all rules.

**How to use:**
1. Copy the contents of `run-session.md` into any AI chat
2. Paste your SCOPE.md when prompted (or provide it as a file)
3. Work through the rounds — the AI challenges you through your defined lenses
4. After all rounds, ask for synthesis

## Tips

- **No file system required.** Both prompts work in pure conversation mode. Saving files is optional.
- **See the example.** Check `scopes/_example/` for a complete worked example (scope, rounds, positions, synthesis).
- **Two chats or one.** You can create a scope and run a session in the same conversation, or use separate chats.
- **Any AI works.** These prompts are designed to work with any AI that can follow markdown instructions.
