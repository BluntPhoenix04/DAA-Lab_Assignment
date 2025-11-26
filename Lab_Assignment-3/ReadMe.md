
# Assignment 3 — Graph Algorithms & Experiments (Notebook)

This folder contains the Jupyter notebook `Assignment_3.ipynb`, which implements a set of graph algorithms and related benchmarking experiments. The notebook provides small example implementations, simple tests, and timing experiments with plots.

## Contents
- `Assignment_3.ipynb` — Notebook cells include:
	- Simple graph neighbor-based function: friend-suggestion (friends-of-friends)
	- Bellman-Ford example (relaxation over weighted edges, can handle negative weights)
	- Dijkstra's algorithm (priority-queue based shortest paths)
	- Prim's algorithm (minimum spanning tree via a priority queue)
	- Lab experiments and plots:
		- BFS time vs graph size
		- Bellman-Ford time vs edge count
		- Dijkstra time vs graph density

## Requirements
- Python 3.8+ (modern Python 3.x is fine)
- Notebook packages:
	- `numpy` (used in some experiment cells)
	- `matplotlib` (for plotting)

Install dependencies with pip:

```powershell
pip install numpy matplotlib
```

## How to run
- Open `Assignment_3.ipynb` in Jupyter Notebook or JupyterLab and run the cells interactively to see outputs and plots.
- Run the whole notebook non-interactively (executes and saves an output copy):

```powershell
jupyter nbconvert --to notebook --execute "Assignment_3.ipynb" --output executed_Assignment_3.ipynb
```

Notes:
- The notebook uses randomness for graph generation in experiments; results vary per run.
- Timing helper `time_function` is implemented in the notebook to measure wall-clock execution time.

## Implementation highlights
- Friend suggestions: collects friends-of-friends by exploring neighbors of neighbors, excluding direct friends and the user.
- Bellman-Ford: demonstrates edge relaxation over |V|-1 iterations; useful for graphs with negative weights.
- Dijkstra: uses `heapq` to implement a priority queue for efficient shortest path computation (non-negative weights assumed).
- Prim: builds an MST incrementally using a min-heap of candidate edges.

## Experiments and plots
- BFS Time vs Graph Size: synthetic graphs with a small fixed average degree; measures BFS runtime as node count increases.
- Bellman-Ford Complexity Growth: randomized edges and weights to observe how runtime grows with node/edge counts.
- Dijkstra Time vs Graph Density: vary edges-per-node to show how density affects Dijkstra's runtime.

## Reproducibility & Tips
- To get reproducible experiments, seed the random generator at the top of the notebook, e.g. `random.seed(0)`.
- Increase the graph sizes or number of trials for smoother timing curves; be aware runtime may increase substantially for some algorithms.

## Suggestions / Next steps
- Add `requirements.txt` with `numpy` and `matplotlib` for convenience.
- Save example output plots to `png` files from the notebook for documentation.
- Add short complexity notes (time/space) for each algorithm directly in the README.

If you'd like any of these changes (requirements file, saved plots, complexity notes, or a git commit), tell me and I'll add them.
