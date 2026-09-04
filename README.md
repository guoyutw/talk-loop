# talk-loop

Evidence-driven conversation skill. Four concrete rules for keeping a conversation on track, plus a talking-head dogfood mode.

**Not autonomous learning.** The model does not rewrite itself. Real conversations motivate lessons, but rule changes are evidence-backed and owner-approved, then versioned.

## What it is

A small, public, MIT-licensed skill you can drop into ChatGPT Voice, Hermes, or any conversational agent:

- **Core**: 4 evidence-backed rules that work beyond YouTube.
- **Mode**: `talking-head` — the current dogfood use case (talking-head video rehearsal with a conversational partner).
- **Loop**: `real conversation → review how it worked → candidate lesson → accumulate evidence → owner-approved change → CHANGELOG`.

## What it is not

- Not a personal memory/profile layer.
- Not a transcript store.
- Not therapy or medical advice.
- Not automation (no cron, DB, self-updater).

## Use

1. Read `SKILL.md` for the 4 core rules.
2. Add `modes/talking-head.md` when rehearsing talking-head video.
3. Use `docs/review-protocol.md` to turn a real conversation into an evidence-backed change.

## Structure

```
README.md
LICENSE
SKILL.md                — 4 core rules
modes/talking-head.md   — dogfood mode, separated from core
docs/review-protocol.md — evidence → candidate → owner approval
CHANGELOG.md
```

## Origin

Distilled from real talking-head rehearsals (`talk-loop` = `talk` + `loop`). See `CHANGELOG.md` for the v0.1 evidence baseline and `docs/review-protocol.md` for how future changes stay de-identified.

## License

MIT — see `LICENSE`.
