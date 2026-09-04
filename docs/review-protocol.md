# Review protocol

How `talk-loop` changes without silent self-rewrite.

## Loop

```
real conversation  →  review how it worked  →  candidate lesson
→  accumulate / assess evidence  →  owner-approved rule change  →  version + CHANGELOG
```

The review evaluates **how the conversation worked** (threading, concrete vs abstract, follow-through), not merely what was discussed.

## Evidence

- A candidate lesson must cite real-conversation evidence to be considered (generalized description, not raw transcript).
- Raw transcripts, private session content, identifying details, and personal profiles stay private and are never published.
- Public rationales in `CHANGELOG.md` are de-identified and generalized.

## Promotion rule

1. A candidate is observed in at least one real conversation and noted as a candidate (not yet core).
2. Additional evidence is accumulated across conversations/sessions.
3. When evidence is judged sufficient, the **owner approves** the promotion explicitly.
4. The change is versioned in `CHANGELOG.md` with the generalized rationale.

No rule is promoted by the model acting alone. No silent self-modification.

## What this protocol does not do

- Does not create automation, cron, database, or a self-updater. The loop is manual and owner-gated.
- Does not claim therapy, medical, or clinically validated counseling.

## Roles

- **Model**: helps articulate the candidate and summarize evidence.
- **Owner**: decides whether evidence is sufficient and approves the change.

## Example

> Candidate: "When the speaker offers a concrete person/event, the partner followed it and the thread extended."
> Evidence (generalized): "In a rehearsal, after the speaker mentioned a specific family member's reaction, a follow-up on that reaction produced the longest natural segment."
> Action: accumulate; promote only after owner approval.
