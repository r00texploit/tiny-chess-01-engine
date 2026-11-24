# tiny-chess-01-engine

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/r00texploit/tiny-chess-01-engine/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/r00texploit/tiny-chess-01-engine/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

An original chess engine in under 4,096 bytes of Python 3.13 (standard
library only) for make.fun's tiny-chess-01 competition. `main.py` is the
whole engine: an LZMA-packed copy of its readable source, written by
`makefun compress`.

- 10x12 mailbox board held as a string from the side to move, rotated
  after every move.
- Negamax alpha-beta with principal-variation search, iterative
  deepening, a transposition table kept for the game, killer and history
  move ordering, null-move pruning, late-move reductions and pruning,
  futility and reverse-futility pruning.
- Check extensions; a quiescence search over captures and promotions that
  searches every evasion when in check at the horizon.
- Piece-square tables blended between opening and endgame, plus a cached
  pawn and king term: passed, isolated and doubled pawns, pawn shelter.
- Repetitions, insufficient material and stalemate score as draws.
- Deterministic: node budgets drawn from a fixed total for the trial,
  never a clock, so a replay plays the same moves.

## Run it

```sh
MAKEFUN_ENV_URL=http://store:8080 python3 -P -s main.py
```

MIT licensed, see `LICENSE`.

---

<sub>Entered on [make.fun](https://make.fun/?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
