# Candidate lessons — 2026-09-13 guided-conversation dogfood

> Status: **accumulating evidence** — not core, not mode, not promoted.
> Follows `docs/review-protocol.md`: candidate lessons noted from real conversation, generalized and de-identified, raw/private evidence stays private. Promotion requires additional evidence and explicit owner approval.

Source session: 2026-09-13 guided-conversation dogfood (generalized). No raw transcript is published here.

---

## 1. Owner-hosted floor passing when speaker identity is unreliable

**Candidate:** In two-humans + AI `guided-conversation`, when the AI cannot reliably identify the current speaker from audio alone, it should not guess speaker identity. Instead, the owner / primary human explicitly hosts the handoff (e.g., "next, let's hear from the other participant"), the AI switches target according to that handoff, and after a brief follow-up returns the floor to the two humans.

**Generalized evidence:** In a real two-humans + AI session, the AI repeatedly mis-identified the speaker, which led to misdirected follow-ups, mis-attributed audio issues, and conversational confusion. When the primary human explicitly hosted the conversation and passed the floor to the other participant, speaker state became more controllable and the exchange more coherent. This also aligns with the `guided-conversation` direction that the AI is a **navigator, not the host**.

**Status:** `accumulating evidence` — observed in one session on 2026-09-13, not yet sufficient for promotion to core or mode. Accumulate across sessions before owner-approved change.

---

## What is not happening in this artifact

- No change to `SKILL.md` core rules (4 rules frozen).
- No change to `modes/guided-conversation.md`.
- No `CHANGELOG.md` promotion entry — promotion is owner-gated and requires more evidence.
- No raw transcript, private content, or identifying detail is included.
- No automation, database, or governance system is introduced.
