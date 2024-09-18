# Sudoku Solver Using Backtracking Algorithm

This project implements a Sudoku solver using a **Backtracking algorithm**. The solver attempts to solve Sudoku puzzles by filling in empty cells one by one, checking whether each entry is valid, and backtracking when it encounters invalid configurations. The project is implemented in Python, with additional helper functions to handle board input/output, validation of moves, and display of the Sudoku grid.

## Key Components:

### 1. Board Representation
The Sudoku board is represented as a Python dictionary, where each cell is accessed by a key in the form of 'A1', 'B2', etc., where the first letter corresponds to the row and the second digit to the column.

### 2. Print and String Conversion Functions
- `print_board(board)`: Displays the Sudoku board in a human-readable 9x9 grid format.
- `board_to_string(board)`: Converts the board's current state into a string format for saving or further processing.

### 3. Move Validation
- `is_valid_move(board, row, col, num)`: Checks if placing a given number in a specific cell is a valid move according to Sudoku rules (row, column, and 3x3 grid checks).

### 4. Backtracking Algorithm
- `solve_sudoku(board, row, col)`: Recursively attempts to fill the board using backtracking. If a valid configuration is found, the puzzle is solved. Otherwise, it backtracks by resetting the current cell and trying different values.
  
### 5. Board Solving
- `backtracking(board)`: Solves the given Sudoku puzzle using the `solve_sudoku()` function. It also prints whether the puzzle was successfully solved or not.

### 6. Input/Output
- The script supports two modes:
  1. **Single Puzzle Mode**: Accepts a single puzzle as input through the command line.
  2. **Batch Mode**: Reads puzzles from a text file and solves them iteratively.

## Running the Sudoku Solver

### Single Puzzle Mode
To solve a single Sudoku puzzle, provide a string of 81 digits (representing the puzzle) as input via the command line:

```bash
python3 sudoku.py "530070000600195000098000060800060003400803001700020006060000280000419005000080079"
python3 sudoku.py

###Example:
Input (Unsolved Sudoku):
5 3 0 | 0 7 0 | 0 0 0
6 0 0 | 1 9 5 | 0 0 0
0 9 8 | 0 0 0 | 0 6 0
---------------------
8 0 0 | 0 6 0 | 0 0 3
4 0 0 | 8 0 3 | 0 0 1
7 0 0 | 0 2 0 | 0 0 6
---------------------
0 6 0 | 0 0 0 | 2 8 0
0 0 0 | 4 1 9 | 0 0 5
0 0 0 | 0 8 0 | 0 7 9

Output (Solved Sudoku):
5 3 4 | 6 7 8 | 9 1 2
6 7 2 | 1 9 5 | 3 4 8
1 9 8 | 3 4 2 | 5 6 7
---------------------
8 5 9 | 7 6 1 | 4 2 3
4 2 6 | 8 5 3 | 7 9 1
7 1 3 | 9 2 4 | 8 5 6
---------------------
9 6 1 | 5 3 7 | 2 8 4
2 8 7 | 4 1 9 | 6 3 5
3 4 5 | 2 8 6 | 1 7 9
