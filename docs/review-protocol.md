# Review protocol

How `talk-loop` changes without silent self-rewrite.

## Loop

Talk Loop is the full iterative method:

```
conversation → post-conversation review → identify effective / ineffective interaction → keep useful adjustments → carry them into the next conversation
```

Shared-rule evolution runs on top of that as:

```
candidate lesson → accumulate / assess evidence → owner-approved rule change → version + CHANGELOG
```

The review evaluates **how the conversation worked** (threading, concrete vs abstract, follow-through), not merely what was discussed. `SKILL.md` is the conversational behavior layer; this document is the review and evolution layer; persistence (below) is what connects one session to the next.

## Evidence

- A candidate lesson must cite real-conversation evidence to be considered (generalized description, not raw transcript).
- Raw transcripts, private session content, identifying details, and personal profiles stay private and are never published.
- Public rationales in `CHANGELOG.md` are de-identified and generalized.

## Persistence boundary

Talk Loop defines *what* to keep (the useful adjustment from review); the host determines *how* it persists.

- **Without persistence:** `conversation + review` still works inside a session, but cross-session improvement cannot be honestly claimed.
- **With persistence:** the kept adjustment is carried into the next conversation via the host — e.g., ChatGPT Memory, custom instructions, manually saved notes/rules, or an external durable-state system (Hermes is one dogfood example, not a requirement).
- Talk Loop does not build a persistence engine, sync layer, or backend, and does not claim learning across sessions where the host provides none.

## Promotion rule

1. A candidate is observed in at least one real conversation and noted as a candidate (not yet core).
2. Additional evidence is accumulated across conversations/sessions.
3. When evidence is judged sufficient, the **owner approves** the promotion explicitly.
4. The change is versioned in `CHANGELOG.md` with the generalized rationale.

No rule is promoted by the model acting alone. No silent self-modification.

## What this protocol does not do

- Does not create automation, cron, database, sync layer, or a persistence engine. The loop is manual and owner-gated; persistence is host-dependent (see above).
- Does not claim therapy, medical, or clinically validated counseling.
- Does not claim cross-session learning where the host provides no persistence.

## Everyday use — one-agent self-review (default)

The default for normal users is lightweight and single-agent:

- The **same agent** that held the conversation does a brief self-review immediately after.
- It is diagnostic: what was missed, where a rule was violated, what evidence and candidate lesson emerged, what to try next time.
- The adjustment applies to the **next conversation in that session** (a reminder, a rephrased instruction). It does not change the shared/public skill.
- No second reviewer, multi-agent workflow, or repo-governance setup is required for this loop.

```
conversation → same-agent self-review → next conversation improves
```

## Two levels of learning

- **Personal / session-level adaptation** — self-review notes and small prompt tweaks that help the next turn. No approval needed; stays private to that user/session.
- **Shared / public skill evolution** — changes to `SKILL.md`, modes, or `docs/` that affect everyone. Requires accumulated evidence and explicit owner approval per Promotion rule below.

A self-review can *propose* a candidate for the shared skill, but cannot self-authorize it.

## What self-review is and is not

- **Is:** a diagnostic check — did the agent follow the 4 rules? Where did it miss? What concrete evidence supports a candidate?
- **Is not:** an authoritative promotion. A candidate does not become a shared rule because the same agent suggested it.

## Outcome ≠ adherence

A conversation can feel productive while the agent still violates the skill (e.g., stacked questions, dropped concrete detail, missed challenge). Review evaluates **rule adherence** separately from **perceived conversation quality** — good outcome does not imply correct adherence.

## When independent review helps (optional escalation)

Independent or second-agent review is **optional**, not the default. Consider it when evaluating whether a candidate should be promoted to a shared rule — extra eyes help judge evidence sufficiency and wording before the owner decides. It is not required for everyday self-review.

## Versioning & reversibility

Iteration is expected. Every material change to the shared skill is committed to Git and summarized in `CHANGELOG.md` with a generalized rationale. Prior states remain inspectable via Git history and can be reverted (`git log` / `git diff` / `git revert`) rather than silently overwritten.

## Roles

- **Model (same-agent reviewer by default)**: holds the conversation, reviews it, and identifies what to keep for next time.
- **Host / environment**: determines how kept adjustments persist to the next session (Memory, instructions, notes, or external state).
- **Optional independent reviewer**: used as escalation when judging promotion of a shared rule, not for every conversation.
- **Owner**: decides whether evidence is sufficient and approves any shared/public change.

## Example

> Candidate: "When the speaker offers a concrete person/event, the partner followed it and the thread extended."
> Evidence (generalized): "In a rehearsal, after the speaker mentioned a specific family member's reaction, a follow-up on that reaction produced the longest natural segment."
> Action: accumulate; promote only after owner approval.
