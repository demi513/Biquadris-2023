# Biquadris

## What I learned
  - Software Design Principles: Applying principles like modularity and extensibility to accommodate future enhancements with minimal changes.
  - Modern C++: Utilized smart pointer, templates and standard containers
  - UML: Learned to design complex programs in UML
  - Data structures: Learned to implement complex data structures like a Trie for comamnd processing


## Overview
Biquadris is a two-player competitive video game inspired by Tetris. Each player has a board of 11 columns and 15 rows where tetrominoes (blocks of four cells) appear at the top and must be strategically placed to avoid gaps. Unlike Tetris, Biquadris is turn-based, allowing players to take their time to decide where to place each block. 
- ![The detailed instructions](./doc/instructions.pdf)
- ![The explanation for design decision](./doc/design.pdf) 

## Game Rules
  - Boards: Each player has a board of 11 columns and 15 rows, with 3 extra rows reserved at the top for block rotation.
  - Blocks: There are seven types of blocks (I, J, L, O, S, Z, T) that can be moved and rotated.
  - Turns: Players take turns dropping blocks. A turn ends when a block is placed on the board.
  - Row Clearing: When a row is completely filled, it disappears, and the blocks above move down by one unit.
  - Game Over: If a block cannot be placed at the top of the board, the game is over for that player.

## Special Features
  - Non-Real-Time: Players have unlimited time to decide where to place a block.
  - Special Actions: Clearing two or more rows simultaneously triggers special actions that negatively affect the opponent.
  - Blind: Covers part of the opponent's board with question marks.
  - Heavy: Makes the opponent's blocks fall faster.
  - Force: Changes the opponent's current block to a block of the player's choosing.

## Difficulty Levels
  - Level 0: Blocks are taken in sequence from predefined files.
  - Level 1: Blocks are randomly chosen with a higher probability for S and Z blocks.
  - Level 2: All blocks are selected with equal probability.
  - Level 3: Similar to Level 1 but blocks are "heavy" and fall faster.
  - Level 4: Includes all Level 3 rules plus additional 1x1 blocks that drop if rows are not cleared frequently.

## Commands
  - Movement: left, right, down
  - Rotation: clockwise, counterclockwise
  - Drop: drop
  - Level Control: levelup, leveldown
  - Randomness Control: norandom, random
  - Testing: sequence file, I, J, L, etc.
  - Game Control: restart
Commands can be prefixed with a multiplier to repeat the action multiple times (e.g., 3left moves the block three cells to the left).

## Scoring
  - Points are awarded for clearing rows and completely removing blocks from the screen.
  - The score is calculated based on the current level and the number of lines cleared.
  - The high score persists until the program terminates.

## Command-Line Options
  - -text: Runs the program in text-only mode.
  - -seed xxx: Sets the random number generator's seed.
  - -scriptfile1 xxx: Uses a specified file for player 1's blocks in Level 0.
  - -scriptfile2 xxx: Uses a specified file for player 2's blocks in Level 0.
  - -startlevel n: Starts the game at the specified level.

## Design Considerations
  - Extensibility: The system is designed to easily accommodate new levels and commands with minimal changes to the source code.
  - Special Effects: The program can handle multiple simultaneous effects without excessive branching.
  - Command Flexibility: The system supports renaming commands and creating macros for sequences of commands.

## Installation and Setup
1. Clone the repository.
2. Run `make`
3. Run `./biquadris`

# Credits
In collaboration with Leo Shi and Hayden Lai
