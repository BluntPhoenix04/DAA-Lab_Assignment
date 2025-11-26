
# Assignment 4 — Crew Scheduling (Notebook)

This folder contains the Jupyter notebook `Assignment_4.ipynb`, which demonstrates a backtracking solution for an airline crew scheduling problem, visualizations, and a small timing experiment to show how runtime grows with the number of flights.

## Contents
- `Assignment_4.ipynb` — Notebook cells include:
	- Backtracking solver for assigning flights to crew members subject to rest-time constraints.
	- A timing experiment measuring backtracking execution time vs number of flights.
	- A Gantt-chart style visualization showing a sample crew assignment schedule.

## Requirements
- Python 3.8+ (or any modern Python 3.x environment)
- Packages used:
	- `matplotlib`
	- `time` (standard library)

Install dependencies with pip:

```powershell
pip install matplotlib
```

## How to run
- Open `Assignment_4.ipynb` in Jupyter Notebook / JupyterLab and run cells interactively to view the solver output and plots.
- Run the whole notebook non-interactively:

```powershell
jupyter nbconvert --to notebook --execute "Assignment_4.ipynb" --output executed_Assignment_4.ipynb
```

## Implementation notes
- The solver assigns flights (tuples `(id, start, end)`) to crew members using recursion and backtracking.
- `MIN_REST` enforces the minimum rest time (in hours) between consecutive flights for the same crew member.
- The `valid` function checks overlap and rest constraints before assigning a flight to a crew member.

## Experiments & Visualization
- Timing experiment: measures how the backtracking solver's runtime grows with the number of flights (example sizes: `[4,6,8,9,10]`).
- Gantt chart: a simple horizontal bar chart that visualizes assigned flights per crew member (useful for verifying scheduling visually).

## Reproducibility & Tips
- The example schedules and timings in the notebook are deterministic given the generation approach; however, the backtracking runtime can vary depending on flight timings and constraints.
- To explore larger problem instances, increase the number of crew members or change flight intervals; caution—backtracking runtime can grow exponentially.

## Next steps / Suggestions
- Add a `requirements.txt` containing `matplotlib` and any other packages used across notebooks.
- Add alternative scheduling heuristics (greedy or interval graph coloring) for larger instances.
- Save the plotted Gantt chart and timing plots to image files from the notebook for documentation.

If you want any of those, tell me and I will add them (requirements file, saved plots, or a short complexity section).
