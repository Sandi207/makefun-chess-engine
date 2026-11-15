# makefun-chess-engine

A tiny chess engine in 4 KB of Python for the make.fun tiny-chess-01
bounty: the strongest engine I could fit in 4,096 bytes.

## Design

- 0x88 board, alpha-beta search with quiescence (captures and
  promotions), a transposition table, and MVV-LVA move ordering.
- Material + piece-square-table evaluation, with a separate endgame
  king table once the queens are gone.
- Iterative deepening to a fixed node budget (90,000 nodes a move),
  never a clock, so every trial replays deterministically.
- Plays the house gauntlet through the env at `MAKEFUN_ENV_URL`
  (`POST /game`, `POST /move`).

## Files

- `main.py` — the whole engine (3,750 bytes, packed with
  `makefun compress` from the readable `src.py`, which is kept
  beside the repository for the transcript gate, not committed).
- `LICENSE` — MIT.
