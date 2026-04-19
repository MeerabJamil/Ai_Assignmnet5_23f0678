Project Overview

This project implements an intelligent Sudoku Solver using Constraint
Satisfaction Problem (CSP) techniques. The solver utilizes a combination of
backtracking search, heuristic variable selection, and constraint propagation to
efficiently find solutions for 9x9 Sudoku puzzles.

Core Features

AC-3 Algorithm: Implements the Arc Consistency Algorithm #3 to prune
search domains and maintain consistency between neighboring cells [cite:
47-60].
Backtracking Search: A recursive depth-first search that explores
potential assignments [cite: 75-87].
MRV Heuristic: Uses the Minimum Remaining Values heuristic to select the
next variable to assign, prioritizing cells with the smallest remaining
domain [cite: 63-66].
Forward Checking: Validates assignments by proactively removing
incompatible values from neighboring cells [cite: 67-72].

Key Functions

Initialization & Setup

get_domains(board): Initializes the possible values (1-9) for each cell
based on the starting board state [cite: 9-19].
get_neighbors(cell): Identifies all related cells in the same row,
column, and 3x3 subgrid [cite: 20-37].

Constraint Propagation

revise(domains, xi, xj): A helper for AC-3 that removes values from
cell xi's domain that have no supporting values in xj [cite: 38-46].
ac3(domains): Processes a queue of cell pairs to reduce the search space
globally [cite: 47-60].
Solving Logic

solve(board): The main entry point that resets performance counters,
applies initial AC-3 pruning, and triggers the backtracking search [cite:
94-107].
backtrack(domains): The recursive engine that manages trial
assignments and keeps track of total calls and failures [cite: 75-87].

Usage

The program reads the Sudoku puzzle from a text file where each line
represents a row of the puzzle [cite: 108-112].
python solver.py
Enter Sudoku file name: puzzle.txt

Upon completion, the solver outputs the original board, the solved board (if a
solution exists), and performance metrics including Backtrack Calls and
Failures [cite: 117-125].
