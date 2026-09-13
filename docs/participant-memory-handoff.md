# Participant memory handoff — `guided-conversation`

> Status: **generic protocol** for `guided-conversation`. No real participant records live here. Local participant cards stay outside public `talk-loop`, Git history, and OneDrive. This file defines the handoff shapes only.

## When this applies

When `modes/guided-conversation.md` is in use and a participant is named. ChatGPT Live is the conversation surface; it does **not** have local memory access.

## Handoff 1 — `PARTICIPANT_LOOKUP` (start)

When a participant is named, ChatGPT **must first emit** a small lookup instead of assuming memory:

```
PARTICIPANT_LOOKUP: {"participant": "王小明"}
```

- One participant per lookup. If two participants, emit two lookups.
- Use the display name as spoken. No ID creation here.
- The user copies this block to Hermes. Hermes resolves it against **local-only participant memory** (outside repos) and returns either:

  - `PARTICIPANT_CONTEXT` — concise context for the next conversation, or
  - `NEW_PARTICIPANT` — clean "no prior context" result

  The user pastes that result back into ChatGPT Live before the conversation proceeds.

Neither `PARTICIPANT_LOOKUP` nor the returned context invents personal data. If Hermes returns `NEW_PARTICIPANT`, ChatGPT treats them as new.

## What Hermes returns

**Repeat participant:**

```
PARTICIPANT_CONTEXT: {"participant": "王小明", "context": "上次聊到一人公司心態轉折，提到澳洲香蕉農場故事很能帶動對話；待續：怎麼把心態轉成 Threads 貼文", "open_threads": ["澳洲故事 → 貼文", "一人公司三個自由的選擇"], "last_session": "2026-09-10"}
```

- `context`: ≤ 500 chars, minimum useful cross-session context / open threads only. No full transcript.
- `open_threads`: 0–3 items, each short. May be empty.
- Sensitive personal information is excluded by default.

**New participant:**

```
NEW_PARTICIPANT: {"participant": "王小明"}
```

No extra fields. ChatGPT does not hallucinate prior context.

## Handoff 2 — review / closeout (`PARTICIPANT_MEMORY_DELTA` or `NO_WRITE`)

At review/closeout ChatGPT **must decide** whether anything is worth carrying forward and emit **exactly one** of:

**A) Worth saving:**

```
PARTICIPANT_MEMORY_DELTA: {"participant": "王小明", "context": "對澳洲故事反應很深，下次可追問當時怎麼決定回台灣；偏好具體例子勝於抽象總結", "open_threads": ["澳洲香蕉農場 → 為什麼回台灣"], "last_session": "2026-09-13"}
```

- `context`/`open_threads` follow the same minimum-useful rule. No full transcript, no sensitive data by default.
- The user copies this block to Hermes. Hermes writes the local participant card **directly without a second confirmation** (if the delta is valid).

**B) Nothing worth saving:**

```
NO_WRITE: {"participant": "王小明", "reason": "no new open thread worth carrying"}
```

Hermes does nothing for `NO_WRITE` except optionally acknowledge.

## Manual transport (no daemon)

The flow is intentionally manual — no daemon, webhook, background sync, API bridge, or automatic ChatGPT↔Hermes transport:

```
ChatGPT Live → PARTICIPANT_LOOKUP → (user copies) → Hermes local lookup → (user copies back) → ChatGPT Live
... conversation / review ...
ChatGPT → PARTICIPANT_MEMORY_DELTA / NO_WRITE → (user copies) → Hermes local write
```

The Generic protocol does not require a specific local filesystem path; the Hermes host chooses the smallest safe implementation from current authority (local-only outside Git/OneDrive).

## What is not persisted

- No full transcripts.
- No sensitive personal information by default (IDs, credentials, health/financial detail, etc.).
- No participant records in public `talk-loop` or Git history or OneDrive. Real records stay local-only on the Hermes host.

## Relationship to other docs

- `modes/guided-conversation.md` — how the conversation is conducted
- `flows/post-from-talk.md` — optional output flow after conversation
- `docs/review-protocol.md` — existing review/evidence/versioning still applies; `DELTA`/`NO_WRITE` is part of review, not a replacement

Future refinements are evidence-driven via `docs/review-protocol.md`; do not redesign core rules for one private preference.
