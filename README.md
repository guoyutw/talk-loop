# talk-loop

An iterative conversation workflow for making AI conversations more suitable through use — not a prompt or autonomous-learning system.

Talk Loop is the method:

```
conversation → post-conversation review → identify effective / ineffective interaction → keep useful adjustments → carry them into the next conversation
```

`SKILL.md` is one execution interface *inside* that workflow (the conversational behavior layer), not the whole product. The workflow defines *what* to keep; the host/environment determines *how* it persists to the next session.

**Not autonomous learning.** The model does not rewrite itself. Real conversations motivate lessons, but shared rule changes are evidence-backed and owner-approved, then versioned.

---

## Quickstart — try it in 30 seconds

`README.md` is for **you** (how to start). `SKILL.md` is the **agent behavior contract** (what the agent does).

1. **Load the core** — Give your conversational agent `SKILL.md` as its interaction policy (one interface inside the workflow).
2. **Add the mode if needed** — Rehearsing talking-head video? Also add `modes/talking-head.md`.
3. **Have a real conversation** — Talk about a real topic; the agent follows the 4 rules.
4. **Review right after** — Use `docs/review-protocol.md` for a lightweight same-agent self-review: what worked, what was missed, what to keep.
5. **Keep what was useful** — Carry the useful adjustment into the next conversation via whatever persistence your host provides (see Persistence below).

### First dogfood example: ChatGPT Live

Paste `SKILL.md` (and `modes/talking-head.md` if rehearsing) into ChatGPT Live as context/instructions, then talk. It works there today because Live accepts supplied instructions — this was the first place `talk-loop` was dogfooded.

Not ChatGPT-only: the same core can be used with any conversational agent that lets you supply reusable instructions or context (e.g., other voice agents, Hermes, or a system-prompt slot). No adapter or install required.

### Before / after (generalized)

*Speaker: "We tried a new product idea but it stalled."*

- **Before (scatters the thread):** "Got it! What was the product? What was the business model? What did you learn? What would you do differently?" — four questions at once; speaker has to choose.
- **After (one thread, follows the heat):** "Who was the first real person who pushed back on it — what did they actually say?" — one question, picks the concrete detail, keeps the thread.

---

## What it is / is not

**Is:** A small, public, MIT-licensed iterative workflow for improving AI conversations through use.

- **Workflow:** `talk → review → retain useful adjustments → reuse next time` — the loop itself is the product.
- **Core:** 4 evidence-backed conversational rules (in `SKILL.md`) that work beyond YouTube.
- **Mode:** `talking-head` — the current dogfood use case.

Loading `SKILL.md` alone is not the full Talk Loop — it is one layer inside the workflow.

**Is not:**
- Not a personal memory/profile layer by itself (persistence is host-dependent — see below).
- Not a transcript store.
- Not therapy or medical advice.
- Not a persistence engine, sync layer, or backend — Talk Loop defines what to keep; the host determines how it survives.
- Not a voice model's low-level speech or turn-taking system — `talk-loop` does not replace speech recognition, voice activity detection, or platform turn-taking; it guides *interaction choices* (what to follow, ask, challenge, or recover) once the turn is yours.

## Structure

```
README.md               — you are here: workflow + how to start
LICENSE                 — MIT
SKILL.md                — 4 core rules (conversational behavior layer — one interface inside the workflow)
modes/talking-head.md   — dogfood mode, separated from core
docs/review-protocol.md — review, persistence, and shared-rule evolution
CHANGELOG.md            — version history
```

Workflow: `conversation → review → retain useful adjustments → reuse next time`. Shared-rule evolution is `candidate → evidence → owner approval → CHANGELOG`. See `docs/review-protocol.md` (public rationales are de-identified; raw/private evidence stays private).

## Persistence is host-dependent

Talk Loop says *what* is worth keeping (the useful adjustment identified in review); the host says *how* it survives to the next session.

- **Without persistence:** you still get `conversation + review` — useful inside one session, but no reliable cross-session accumulation.
- **With persistence:** the kept adjustment is carried into the next conversation (e.g., via ChatGPT Memory, custom instructions, manually saved notes/rules, or an external durable-state system). Different users can use different mechanisms — Hermes is one maintainer/dogfood implementation, not a requirement.
- Talk Loop does not build a memory system for you and does not claim cross-session learning where the host provides no persistence.

## The default loop — lightweight, one agent

For everyday use you don't need a second reviewer or extra tooling:

```
conversation → same-agent self-review → next conversation improves
```

The same agent that held the conversation can do an immediate self-review right after: what it missed, where it violated the 4 rules, and one small adjustment for next time. That adjustment lives in the session — it makes the *next* conversation better without changing the shared skill.

## Two levels — don't mix them

- **Level 1 — Personal / session-level:** Your agent's self-review notes, reminders, or prompt tweaks for the next conversation. No approval needed; stays with you.
- **Level 2 — Shared / public rule:** A change to `SKILL.md`, a mode, or any file in this repo that affects everyone. This requires evidence across conversations and explicit owner approval (see `docs/review-protocol.md`). A self-review can *propose* a candidate, but cannot self-authorize a shared rule.

Self-review is diagnostic, not authoritative. And a conversation can feel good while still violating the rules — review checks adherence separately from outcome.

Iterating is expected. Every material change to the shared skill is committed to Git and noted in `CHANGELOG.md`, so prior states stay inspectable and reversible (`git log`, `git diff`, `git revert`).

## Origin

Distilled from real talking-head rehearsals (`talk-loop` = `talk` + `loop`). See `CHANGELOG.md` for the v0.1 evidence baseline.

## License

MIT — see `LICENSE`.
