# post-from-talk — Threads output flow

> Status: **MVP / dogfood**. **Not an interaction mode.** Optional output / closeout stage **after** a Talk Loop conversation has produced useful material. Reuses the existing `docs/review-protocol.md` loop for improvement.

## When to use

After you have spoken naturally and useful material has emerged — whether via `modes/talking-head.md` or `modes/guided-conversation.md` or plain Talk Loop conversation. You want to turn what you **already said** into a publishable Threads post without switching into a separate AI copywriting workflow.

- Interaction modes (`talking-head`, `guided-conversation`) govern **how the conversation is conducted**.
- `post-from-talk` governs **how you close out to a post** after the conversation, where applicable.
- If no useful material emerged yet, keep talking — do not invoke the output flow to invent material.

## Source of truth

The owner's **actual spoken meaning and wording** from the conversation. Input may be normal ChatGPT speech recognition or a lightly polished transcript (e.g., Typeless), but the output must stay **grounded in what the owner actually expressed**.

If the owner did not say it, the output does not add it.

## Transformation boundary

**Allowed** — bounded editorial operations only:

- select, delete, reorder
- light smoothing (fix disfluency, grammar, repetition)
- punctuation
- Threads-friendly line breaks / spacing

**Not allowed** — do not invent or inject:

- new arguments, insights, hooks, punchlines, CTA, or social-copy framing the owner did not express
- marketing/formula upgrades, mandatory hooks, "golden lines," creator templates, or fixed post templates
- a generic "humanized" style optimization that drifts from the owner's voice

Optimize for **preserving the owner's voice**, not for a generic humanized or viral style. Do not require Meta AI or any other model to draft the post first.

## How it relates to modes

```
[talking-head | guided-conversation | plain Talk Loop] → conversation → (optional) post-from-talk → review
```

- Use one interaction mode at a time where applicable; `post-from-talk` does **not** compete with them.
- It can be invoked after either mode without modifying mode behavior.

## Review and evolution

The existing Talk Loop review loop covers this flow — no separate improvement framework:

- A normal post-conversation review may evaluate **both** the conversation behavior and the final post output.
- Feedback such as "I would not say this," "AI added this," "this was over-polished," or "keep this treatment" may become **evidence / candidates** under `docs/review-protocol.md`.
- Do not promote speculative voice or style rules without repeated evidence. Promotion remains `candidate → evidence → owner approval → version + CHANGELOG` per `docs/review-protocol.md`.

## What this flow does not do

- Does not redesign the 4 frozen core rules in `SKILL.md`.
- Does not turn into a standalone social-copywriting or humanizer system.
- Does not add mandatory hooks, CTA, golden lines, or templates.
- Does not require or assume a specific STT / Typeless / microphone / audio-routing implementation.
- Does not modify `talking-head` or `guided-conversation` behavior.
