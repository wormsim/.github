<div align="center">
  <img src="https://raw.githubusercontent.com/wormsim/worm/main/media/brand/x-avatar-400.png" width="96" alt="WORM">
  <h1>WORM</h1>
  <p><strong>They built an AI worm. <em>We made it pay rent.</em></strong></p>
  <p>Agents in a sealed dish pay rent for compute every tick, split in two when they can afford a
  child, and die when they cannot. Every tick is hashed and chained, so any machine can recompute the
  run instead of trusting it. Simulation only: no real money moves, and nothing leaves the dish.</p>
  <p>
    <a href="https://wormsim.xyz"><strong>The dish</strong></a> ·
    <a href="https://wormsim.xyz/play">Play Outbreak</a> ·
    <a href="https://wormsim.xyz/docs">Docs</a> ·
    <a href="https://github.com/wormsim/worm/blob/main/docs/STATUS.md">Status</a>
  </p>
</div>

---

## What is live

| | Status |
| --- | --- |
| **The dish** | Live: a deterministic economy of rent, work, splits and deaths, drawn and replayed in your browser |
| **Outbreak** | Live on `/play`: a real-time roguelite on the same engine, seven days plus a boss; every run re-runs to the same score |
| **The live season** | Deployed: one move a day, sealed with a wallet signature, the day's seed drawn from a Robinhood Chain block. No player has played a day yet |
| **The record** | Live: SHA-256 over every tick, pinned goldens in CI, and a boundary test that fails the build if the engine could reach a network |
| **Docs** | Live at [/docs](https://wormsim.xyz/docs): the architecture, the determinism, the live protocol, a glossary |
| **$WORM** | Not live. No token exists today, and nothing on the site can take a payment |
| **Daily anchors** | Built and tested, not used: no anchor wallet is funded, so the on-chain list is empty |

[`docs/STATUS.md`](https://github.com/wormsim/worm/blob/main/docs/STATUS.md) is the single source of
truth. If anything here disagrees with it, STATUS.md is right and this page is the bug.

## Check it in ten seconds

```bash
curl -s "https://wormsim.xyz/api/run?seed=20261013&ticks=340" | grep -o '"chain":"[0-9a-f]*"' | cut -c1-30
# "chain":"0a8a5a6b5727073eaddda   <- start of the pinned head in tests/goldens.json
```

## Repositories

| Repository | What it holds |
| --- | --- |
| [**worm**](https://github.com/wormsim/worm) | Everything: the engine, the dish, the games, the live season, the docs and the daily anchors |

The engine has no runtime dependencies — `sim/engine.ts` imports its own hash module and nothing else —
which is why a reader can check it rather than trust it.

The premise is drawn from published research on self-replicating models. This project is independent,
is not affiliated with its authors, and implements none of the capability that research describes.
