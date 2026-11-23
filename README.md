# TinyChess 4KB — speedrun book + search

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/chongphoshun/makefun-tiny-chess-01-book/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/chongphoshun/makefun-tiny-chess-01-book/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB Python chess engine for the make.fun tiny-chess-01 bounty. It plays
the practice gauntlet from a precomputed speedrun book — the fastest forced
wins Stockfish found against each house engine — and falls back to a real
search (0x88 alpha-beta with PVS, transposition table, null-move pruning and
LMR, fixed 100,000 nodes per move) on any position the book does not cover,
including the final's fresh openings.

## Run it

```sh
MAKEFUN_ENV_URL=http://localhost:8080 python3 main.py
```

`main.py` is the packed entrypoint (built from `src.py` with the kit's
`node cli/makefun.mjs compress`). It talks to the trial env over HTTP
(`POST /game`, `POST /move`), plays every game of the gauntlet, and is fully
deterministic: fixed node budget, no clock, no randomness.

---

<sub>Entered on [make.fun](https://make.fun/?ref=6a0zrzzd&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
