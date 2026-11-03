## AIchessbot: UCI Chess Engine

**Project description:** AIchessbot is a chess engine I wrote from scratch. It started as a pure-Python prototype on top of python-chess, and I rewrote it in C++17 for speed. It speaks the standard UCI protocol, so it plugs into any chess GUI (Arena, Cute Chess, Banksia) and can play other engines head to head. Estimated strength is about 3100 Elo.

### How it thinks

- **Board and move generation:** bitboards with magic-bitboard sliding attacks, full make/unmake, and incremental Zobrist hashing, verified with perft node counts
- **Search:** iterative deepening alpha-beta with aspiration windows, principal variation search, null-move pruning, late move reductions, futility pruning, razoring, check extensions, and quiescence search
- **Move ordering:** transposition-table move first, then captures ranked by MVV-LVA and static exchange evaluation, killer moves, and history heuristics
- **Evaluation:** an NNUE neural network evaluator, with a hand-crafted fallback (tapered piece-square tables, pawn structure, king safety, mobility)

### What makes it strong

- **Lazy SMP:** searches on every CPU core at once, with threads sharing one transposition table
- **Syzygy endgame tablebases:** plays perfect endgames once 5 or fewer pieces are left
- **Opening book:** reads Polyglot books and picks weighted grandmaster moves in the opening
- **Pondering:** keeps thinking on the opponent's time

### Tuning and testing

I wrote a Texel tuner that fits the hand-crafted evaluation weights to a labeled dataset of positions by minimizing prediction error. A test suite covers perft correctness, self-play, low-time-control stress tests, long games, and a benchmark that reports nodes per second.

### Tech Stack

C++17 (Make/CMake, builds on Windows, macOS, and Linux), the Fathom library for tablebase probing, and Python for the original prototype and test harnesses.

[View the code on GitHub](https://github.com/atatti-240/AIchessbot)

[← Back to Portfolio](/)
