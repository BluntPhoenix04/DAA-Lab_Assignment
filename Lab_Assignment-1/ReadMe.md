# Assignment 1 — Data Structures & Algorithms (Notebook)

This folder contains an interactive Jupyter notebook `Assignment_1.ipynb` implementing and demonstrating several fundamental algorithms. The notebook includes implementations, simple tests, and a timing/benchmark experiment with visual plots.

## Contents
- `Assignment_1.ipynb` — Main notebook with code cells for:
  - Utility: `time_function` helper for measuring function execution time.
  - Fibonacci algorithms: recursive and dynamic programming (DP) implementations and comparisons.
  - Search: iterative binary search implementation and example.
  - Sorting algorithms: bubble sort, selection sort, insertion sort, merge sort, quick sort (implementations and sample runs).
  - Lab experiment: timing comparisons across sorting algorithms for various input sizes and a matplotlib performance plot.

## Requirements
- Python 3.8+ (or any modern Python 3.x)
- Packages used in the notebook:
  - `numpy`
  - `matplotlib`

You can install dependencies with pip if needed:

```powershell
pip install numpy matplotlib
```

## How to run
- Recommended: Open `Assignment_1.ipynb` in Jupyter Notebook / JupyterLab and run cells interactively.
- Quick non-interactive run (will execute all cells):

```powershell
jupyter nbconvert --to notebook --execute "Assignment_1.ipynb" --output executed_Assignment_1.ipynb
```

Note: the notebook uses random inputs for benchmarks; running the timing cells multiple times may yield slightly different timings.

## Notable implementation details
- `time_function(fn, *args, repeat=3)` measures average runtime across `repeat` runs using `time.perf_counter()`.
- Fibonacci implementations show exponential-time recursion vs. linear-time DP memoization.
- Sorting implementations are written in plain Python for pedagogical clarity (no in-place optimizations beyond simple copies). Merge and Quick sorts are implemented recursively.
- A small experiment in the notebook times each sorting algorithm for increasing input sizes (e.g., `[100,200,400,600,800]`) and plots results using `matplotlib`.

## Reproducibility
- To reduce variance in timing experiments, you can:
  - Increase `repeat` when calling `time_function`.
  - Seed the random generator at the top of the notebook (e.g., `random.seed(0)`).

## Where to edit
- The primary code is in the notebook cells. If you want the timing sizes, plots, or algorithms changed, edit the corresponding cells and re-run.

## Contact / Notes
- This README is auto-generated from the notebook contents. If you want a different format or more details (e.g., algorithmic complexity, inline plots saved to files, or example outputs), tell me what to add and I will update the README.
