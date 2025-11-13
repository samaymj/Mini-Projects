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

## Outcome / expected result

* Running the script on a supported terminal will show the BFS exploration animated with the current path highlighted in red. When the algorithm reaches `X`, the final path remains visible.
* If the maze is unsolvable (no path), the program will finish exploring without finding `X`.

---

## Files you should include in the repo

* `maze_curses.py` — your script.
* `README.md` — this file (rename as appropriate).
* `.gitignore` — suggested content below.
* `LICENSE` — MIT or any license you prefer.
* `requirements.txt` — optional, list `windows-curses` for Windows users.

### Example `.gitignore`

```
__pycache__/
*.pyc
.env
.vscode/
.DS_Store
```

### Example `requirements.txt`

```
# only needed for Windows
windows-curses
```

---

## Step-by-step: Create repository and push code to GitHub

Follow these steps **exactly** in your terminal. Replace `your-username` and `maze-curses` with your values.

1. Create a folder and move your code into it

```bash
mkdir maze-curses
cd maze-curses
# save your script as maze_curses.py
```

2. Initialize git and make the first commit

```bash
git init
git add maze_curses.py README.md .gitignore LICENSE requirements.txt
git commit -m "chore: initial commit — add maze_curses BFS solver and README"
```

3. Create a repository on GitHub

* Option A (recommended): go to github.com ➜ New repository ➜ name `maze-curses` ➜ create.
* Option B (command line using GitHub CLI):

```bash
gh repo create your-username/maze-curses --public --source=. --remote=origin --push
```

(If you use `gh`, you must have GitHub CLI installed and authenticated.)

4. Link local repo to GitHub (if you used GitHub website create)

```bash
git remote add origin https://github.com/your-username/maze-curses.git
git branch -M main
git push -u origin main
```

5. Verify on GitHub web UI that files show up. Add a repository description and topics (`python`, `curses`, `maze`, `bfs`).

6. Add a release tag (optional)

```bash
git tag -a v0.1 -m "v0.1: initial working version"
git push origin v0.1
```

---

## How to run (developer / user instructions)

### Linux / macOS / WSL

1. Open a terminal with support for `curses` (most terminal emulators).
2. Run:

```bash
python3 maze_curses.py
```

### Windows

1. Install the compatibility package:

```bash
pip install windows-curses
```

2. Run the script in a terminal that supports ANSI (Windows Terminal, PowerShell):

```bash
python maze_curses.py
```

### Troubleshooting

* If colors or output look wrong: ensure the terminal supports at least 16 colors and your `$TERM` is set correctly (e.g., `xterm-256color`).
* If the program freezes: press a key (the script waits for `stdscr.getch()` at the end). If it crashes on `curses` init on Windows, install `windows-curses`.

---

## Suggested README sections for GitHub (short version)

* Project title and one-line description
* Demo GIF or screenshot (optional) — instructions below on how to record
* How to run
* Requirements
* License
* Contributing

### Recording a demo

To create a short demo GIF on Linux/macOS, you can use `asciinema` or record the terminal with `simplescreenrecorder` and convert to GIF. For a quick animated GIF, `asciinema` is highly recommended.

---

## Example commit messages (conventional)

* `feat: add BFS maze solver and animation`
* `fix: prevent marking walls as visited`
* `chore: add README, .gitignore, LICENSE`
* `docs: update usage instructions`

---

## Code improvements and future ideas

* Separate maze data into a JSON or text file to allow loading different maps.
* Add command-line arguments (`--delay`, `--maze-file`, `--algorithm=bfs|dfs|astar`).
* Implement A* with a Manhattan/Euclidean heuristic for faster pathfinding.
* Show explored nodes differently from current path (e.g., `.` for visited).
* Add unit tests for `find_neighbors`, `find_start`, and `find_path` logic using `pytest`.
* Add automated CI to run tests on push (GitHub Actions).

---

## Contribution guidelines (short)

* Fork ➜ create a feature branch (`feat/your-feature`) ➜ make changes ➜ open a pull request.
* Use `flake8`/`black` for formatting. Provide tests for logic changes.

---

## License

I suggest MIT. Example `LICENSE` header:

```
MIT License

Copyright (c) 2025 Your Name

Permission is hereby granted, free of charge, to any person obtaining a copy
...
```

---

## Final checklist before publishing

* [ ] Add `README.md` (this document)
* [ ] Add `maze_curses.py`
* [ ] Add `.gitignore` and `requirements.txt` (if needed)
* [ ] Add `LICENSE`
* [ ] Create GitHub repository and push
* [ ] Add a short description and topics on GitHub
* [ ] Optionally add screenshots/GIF and tag a release

*If you want, I can also:*

* create `README.md` and `.gitignore` content as separate files for you to copy, or
* generate a ready-to-commit `LICENSE` (MIT) file, or
* produce a small `CONTRIBUTING.md` and `requirements.txt`.

(End of document)
