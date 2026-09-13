# CHANGELOG

All notable changes to `talk-loop` will be documented here. The model does not update this file on its own; every entry is owner-approved.

## [0.3.0] — 2026-09-13

Owner-approved material change via Issue #38.

### Added

- **Output flow** — `flows/post-from-talk.md` — speech-first Threads output flow (not a mode). After useful material has emerged (usable after `talking-head` or `guided-conversation` where applicable), organizes what the owner actually said into a publishable Threads post. Source of truth is the owner's actual spoken meaning/wording; allows only bounded editorial operations (select, delete, reorder, light smoothing, punctuation, Threads-friendly line breaks). Forbids inventing new arguments, hooks, punchlines, insights, CTA, or social-copy framing; preserves owner's voice rather than optimizing for generic humanized style. Reuses existing `docs/review-protocol.md` loop — review may evaluate conversation and post output, feedback like "I would not say this" can become evidence/candidates; no speculative promotion.

### Unchanged

- **Core (4 rules)** — frozen v0.1 core in `SKILL.md` unchanged.
- **Modes** — `talking-head` and `guided-conversation` unchanged; `post-from-talk` is an output flow, not a third interaction mode.

## [0.2.0] — 2026-09-13

Owner-approved material change via Issue #37.

### Added

- **Mode** — `modes/guided-conversation.md` — two humans + AI navigation (MVP). A live three-party shape where the AI acts as a conversation navigator (not primary host), may directly follow up with either human on a useful concrete thread, supports lightweight optional pre-conversation context without a required question list, and offers a single easy recallable foothold when the conversation stalls. Layers on the frozen 4 core rules; `follow the heat` remains in force. `talking-head` remains distinct (one main speaker thinking aloud vs two humans in conversation). Future refinements remain evidence-driven via `docs/review-protocol.md`.

### Unchanged

- **Core (4 rules)** — frozen v0.1 core in `SKILL.md` unchanged.

## [0.1.0] — 2026-09-04

Initial public release. Minimal, understandable, evidence-driven.

### Added

- **Core (4 rules)** — frozen v0.1 core in `SKILL.md`:
  1. One thread at a time
  2. Follow the heat
  3. Concrete recovery
  4. Challenge when it matters

  Each rule was distilled from real talking-head rehearsals and written to work beyond YouTube. No additional core rules are added in v0.1.

- **Mode** — `modes/talking-head.md` as the first and only dogfood mode (talking-head rehearsal). Separated from core so the core remains usable for other conversational settings.

- **Review protocol** — `docs/review-protocol.md`: `real conversation → review → candidate → evidence → owner approval → version`. Public rationales are generalized; raw/private evidence stays private. No automation, no self-rewrite.

- **Docs** — `README.md`, `LICENSE` (MIT), `SKILL.md`, `modes/talking-head.md`, `docs/review-protocol.md`, `CHANGELOG.md` — the six artifacts required by the frozen spec, with no private transcript/profile content.

### Evidence baseline (generalized)

v0.1 rules summarize patterns observed across talking-head rehearsals where a conversational partner helped the speaker think out loud. De-identified examples: multi-question stacking fragmented threads; following a concrete person/event extended them; rephrasing an abstract question kept the speaker stuck while switching to a concrete slice recovered momentum; and agreeable continuation preserved questionable premises.

Future changes will cite similarly generalized evidence, not raw transcripts, and will appear here only after owner approval.

### Not in v0.1 (candidates held)

Adaptive intervention strength, `有路線沒台詞` / route-map pullback, flow-state silence, stuck-only hints, and automation remain candidates under observation per the frozen spec.

[0.1.0]: https://github.com/guoyutw/talk-loop/releases/tag/v0.1.0
