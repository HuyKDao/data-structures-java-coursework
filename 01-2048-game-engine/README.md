# 2048 Game Engine

**Course:** CS 61B, Data Structures (UC Berkeley, Fall 2022), Project 0

**Goal:** implement the core rules of the sliding-tile game 2048 behind a provided graphical interface.

## What I did
- Wrote the **tilt** logic that slides every tile in one direction and merges equal neighbors. It follows the game's rules: a merged tile can't merge again in the same move, and when three equal tiles line up, the leading two merge.
- Handled all four directions with one algorithm by rotating the board's **viewing perspective**, so the merge code only had to be written once.
- Kept score as tiles merge and wrote the end-of-game checks: whether any empty square exists, whether the 2048 tile has been reached, and whether any legal move remains.
- Worked against the course's JUnit test suites for each rule (empty space, max tile, at least one move, single-direction tilts).

## What I learned
- Breaking a tricky rule set into small helper checks makes the main algorithm much easier to get right.
- Reusing one code path through a change of perspective removes a whole class of copy-and-paste bugs.

## Skills and tools
Java, 2D grid algorithms, game state management, edge-case handling, JUnit, IntelliJ.
