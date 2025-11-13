# Maze Solver (curses) — README

## Project overview

A simple Python maze visualizer and breadth-first-search (BFS) solver using the `curses` library. The program animates the BFS search from the start `O` to the goal `X` on a terminal grid.

This repository contains:

* `maze_curses.py` — the main script (the code you provided).
* `README.md` — this document.
* `.gitignore` — recommended entries.
* `LICENSE` — suggested license (MIT by default).

---

## What I learned

* How to use Python's `queue.Queue` to implement BFS and store paths.
* How to animate terminal output using the `curses` library: `stdscr.addstr`, color pairs, `stdscr.refresh()` and `stdscr.getch()`.
* Terminal coordinate mapping (rows, columns) and simple ASCII grid rendering.
* Handling visited nodes, neighbor generation and basic maze representation as a 2D list.
* Portability caveat: `curses` works natively on Unix-like systems; on Windows you need the `windows-curses` package.

---

## Outcome 

* Running the script on a supported terminal will show the BFS exploration animated with the current path highlighted in red. When the algorithm reaches `X`, the final path remains visible.
* If the maze is unsolvable (no path), the program will finish exploring without finding `X`.

---
