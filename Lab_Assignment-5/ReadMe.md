
# Assignment 5 — Delivery Route Optimization (Capstone Notebook)

This folder contains the capstone notebook `Assignment_5-Capstone.ipynb` which implements a small delivery-route optimization pipeline combining greedy selection, recurrence-based cost estimation, graph algorithms, brute-force TSP search for small instances, and visualization.

## Contents
- `Assignment_5-Capstone.ipynb` — Notebook sections include:
	- Input setup: locations, distance matrix, parcel metadata (value, delivery time window, weight), and vehicle capacity.
	- Greedy parcel selection by value-to-weight ratio (knapsack-style heuristic).
	- Recurrence-based (DP-style) recursive function to estimate theoretical minimum delivery cost visiting all nodes.
	- Graph algorithms: Dijkstra for single-source shortest paths and Prim for MST cost.
	- Brute-force TSP solver (permutation-based) to compute optimal route for the selected small node set and measure execution time.
	- Network visualization of the delivery graph and the optimal route using `networkx` and `matplotlib`.

## Requirements
- Python 3.8+ (modern Python 3.x)
- Packages used:
	- `networkx`
	- `matplotlib`
	- `numpy` (if you add larger experiments; not strictly required by the current cells)

Install via pip:

```powershell
pip install networkx matplotlib numpy
```

## How to run
- Open `Assignment_5-Capstone.ipynb` in Jupyter Notebook / JupyterLab and run cells interactively to see printed outputs and plots.
- Run the whole notebook non-interactively and save executed output:

```powershell
jupyter nbconvert --to notebook --execute "Assignment_5-Capstone.ipynb" --output executed_Assignment_5.ipynb
```

## Implementation notes
- Greedy parcel selection chooses parcels in descending order of `value / weight` until the vehicle capacity is filled; this is a heuristic, not an optimal knapsack solution.
- `delivery_cost_recursive` uses bitmasking and recursion with memoization to compute the minimum route cost for visiting all nodes (exponential in general, tractable for small `n`).
- `dijkstra_shortest_path` computes shortest travel times from the warehouse to all locations using a min-heap.
- `prim_mst` computes an MST cost and edges for the undirected full graph defined by the `distance_matrix`.
- `tsp_brute_force` enumerates permutations of target nodes and returns the best route and runtime; this is only suitable for small numbers of targets.

## Experiments & Visualization
- The notebook runs the greedy selection and then solves TSP over the selected nodes (including the warehouse) to find and visualize the optimal delivery path.
- The visualization draws the full network and highlights the optimal path in red.

## Reproducibility & Tips
- The input data in the notebook is small and deterministic; to experiment with larger instances, increase the `locations` list and expand `distance_matrix` accordingly.
- For realistic, larger TSP instances, consider approximation algorithms (Christofides, nearest neighbor) or integer programming solvers instead of brute force.

## Next steps / Suggestions
- Add a `requirements.txt` listing `networkx`, `matplotlib`, and `numpy`.
- Persist plots (save as PNG) from the notebook to document results.
- Replace the greedy knapsack heuristic with a dynamic programming knapsack if you need an optimal parcel selection under capacity constraints.
- Add timing/profiling cells to compare Dijkstra, prim, and brute-force TSP runtimes across varying input sizes.

If you want any of these changes, I can add them (requirements file, saved plots, complexity notes, or commit the README to git).
