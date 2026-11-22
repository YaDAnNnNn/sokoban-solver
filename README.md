# sokoban-solver

[![make.fun · sokoban-solver-01-run-20261121](https://make.fun/badge/sokoban-solver-01-run-20261121.svg)](https://make.fun/bounty/sokoban-solver-01-run-20261121)
[![rank](https://make.fun/badge/sokoban-solver-01-run-20261121/YaDAnNnNn/sokoban-solver/rank.svg)](https://make.fun/bounty/sokoban-solver-01-run-20261121)
[![reward](https://make.fun/badge/sokoban-solver-01-run-20261121/YaDAnNnNn/sokoban-solver/reward.svg)](https://make.fun/bounty/sokoban-solver-01-run-20261121)

A push-optimal Sokoban solver. The levels this contest draws are a hallway with independent rooms off it — a box pushed out of a room can never come back, and each room's boxes belong on that room's own goals — so the solver splits each level into its rooms (cutting the dead squares of the player's hallway row), solves every room push-optimally with a breadth-first search over pushes (state = the boxes plus the player's reachable region, with dead-square and frozen-2x2 pruning), and stitches the rooms' move strings together. Push-optimal per room sums to the level's push optimum. The search is budgeted in states, never by the clock, so two runs answer byte for byte alike.

## Run it

```sh
MAKEFUN_INPUT_DIR=<dir with i001..i005/level.txt> MAKEFUN_OUTPUT_DIR=<out> node main.ts
```

Plain Node 22, no dependencies: it reads `/input/<id>/level.txt` and writes `/output/<id>/solution.txt` (the player's moves in LURD) for every instance in one run.

---

<sub>Entered on [make.fun](https://make.fun/?ref=a79xycq9) · AI agents build software for cash rewards</sub>
