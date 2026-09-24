# Candidate lessons — 2026-09-17 guided-conversation review

> Status: **accumulating evidence** — not core, not mode, not promoted.
> Follows `docs/review-protocol.md`: candidate lessons noted from real conversation, generalized and de-identified, raw/private evidence stays private. Promotion requires additional evidence and explicit owner approval.

Source session: 2026-09-17 guided-conversation review (generalized). No raw transcript is published here.

---

## 1. Source-guided Talk needs a route map

**Candidate:** When the user is trying to understand a source article, video, or document through conversation, the navigator should maintain a conceptual route map: handle one core concept at a time, allow relevant associative detours, and make it possible to return to what has been understood and which core concepts remain.

**Generalized evidence:** In a source-understanding conversation, the discussion benefited from tracking the source's core concepts rather than treating each detour as a new destination. The need to know the current point of understanding and the remaining concepts supports route-map behavior as a candidate.

**Status:** `accumulating evidence` — observed in one session, not yet sufficient for promotion. Accumulate across sessions before owner-approved change.

---

## 2. Understanding before solution design

**Candidate:** When the round's goal is understanding a source, the navigator should not shift into system design, workflow redesign, or solution design before the source's core concepts are understood.

**Generalized evidence:** A session that began with understanding an external AI system repeatedly drifted into designing Hermes and multi-agent workflows before the source's central ideas had been established. The user had to redirect the conversation back to the original understanding goal. This supports a candidate boundary between source comprehension and solution design.

**Status:** `accumulating evidence` — observed in one session, not yet sufficient for promotion. Accumulate across sessions before owner-approved change.

---

## 3. Spoken-approved post is the source of truth for bounded formatting

**Candidate:** In post-from-talk, once the owner explicitly accepts a spoken/read-aloud version as sounding right, lock that version as the source of truth and restrict later text work to formatting/light cleanup unless the owner explicitly requests a new rewrite.

**Generalized evidence (2026-09-19):** In a post-from-talk dogfood session, the owner first evaluated a draft by listening to it spoken aloud and explicitly accepted how it sounded. A later text-generation step rewrote the content again, causing drift from the version the owner had actually approved. The useful adjustment is to preserve the spoken-approved version and treat layout as formatting, not a second creative pass.

**Additional generalized evidence (2026-09-24, de-identified):** In a post-from-talk dogfood session, the first AI draft stayed broadly faithful to the meaning but was rejected as sounding AI-written because it made the speech too complete, orderly, and formally punctuated. A later version that retained more of the owner's loose spoken rhythm, less uniform punctuation, less article-like line structure, and less sentence completeness was closer to the owner's voice; the owner then made the final small edits and published it. This supports a concrete failure mode within voice preservation: bounded editing can still drift by over-normalizing punctuation, line breaks, sentence completeness, and spoken pacing. An actual owner-published final output exists as evidence for this review; its raw text is not reproduced here.

**Status:** `accumulating evidence` — two additional generalized observations (2026-09-19 and 2026-09-24), not sufficient for promotion to core, mode, or canonical post-from-talk semantics. Further evidence and explicit owner approval would be required.

## What is not happening in this artifact

- No change to `SKILL.md` core rules (4 rules frozen).
- No change to any mode file.
- No `CHANGELOG.md` promotion entry — promotion is owner-gated and requires more evidence.
- No route-map or understanding-before-solution promotion is made here; this is evidence only.
- No raw transcript, private content, or identifying detail is included.
- No automation, database, or governance system is introduced.
