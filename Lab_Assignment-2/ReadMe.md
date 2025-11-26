
# Assignment 2 — Data Structures & Algorithms (Notebook)

This folder contains the interactive Jupyter notebook `Assignment_2.ipynb`, which implements and demonstrates several algorithmic problems and experiments related to greedy algorithms, dynamic programming, backtracking, and brute-force complexity analysis.

## Contents
- `Assignment_2.ipynb` — Notebook with code cells covering:
	- Job Sequencing with Deadlines (Ad scheduling / revenue maximization)
	- 0/1 Knapsack (dynamic programming solution)
	- Sudoku Solver (backtracking solver and validator)
	- Brute-force password-time estimates (combinatorics and time-to-attack calculations)
	- Lab experiments and plots:
		- Job sequencing: number of ads vs total revenue plot
		- Knapsack: budget vs maximum profit plot
		- Sudoku: solver runtime vs number of empty cells
		- Brute-force: password length vs time estimate

## Requirements
- Python 3.8+ (any modern Python 3.x should work)
- Packages used in the notebook:
	- `numpy`
	- `matplotlib`

Install dependencies with pip if needed:

```powershell
pip install numpy matplotlib
```

## How to run
- Recommended: open `Assignment_2.ipynb` in Jupyter Notebook or JupyterLab and run cells interactively to see outputs and plots.
- Non-interactive execution (runs all cells and saves an executed copy):

```powershell
jupyter nbconvert --to notebook --execute "Assignment_2.ipynb" --output executed_Assignment_2.ipynb
```

Notes:
- The notebook uses random inputs for the lab/benchmarking cells; different runs will yield different numeric results.
- Some timing helpers assume a simple `time_function` wrapper; if missing, a minimal timing helper is provided inline in a few cells.

## Implementation highlights
- Job Sequencing: greedy approach — ads sorted by profit and placed into available deadline slots by checking from the ad's deadline downwards.
- Knapsack 0/1: classic DP table `dp[i][w]` computing max profit for first `i` items and capacity `w`.
- Sudoku Solver: standard backtracking with row/column/3x3-block validity checks.
- Brute-force estimation: combinatorics-based computation of total combinations and division by guesses-per-second to estimate required time.

## Reproducibility & Tips
- To reduce variance in experiments, seed the random generator at the top of the notebook, e.g. `random.seed(0)`.
- Increase the number of trials or aggregate across multiple runs for more stable timing curves.

## Next steps / Options
- Add a `requirements.txt` file listing the notebook dependencies.
- Save example outputs (plots) to `png` files from inside the notebook for documentation.
- Expand the README to include algorithmic complexity (time/space) per implementation.

If you want any of those changes, tell me which and I'll update the notebook or add supporting files.
