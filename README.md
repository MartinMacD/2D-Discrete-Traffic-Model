# 2D Discrete Traffic Model
Created in Python within a Jupyter notebook, the aim of this 2D discrete traffic model is to run analyses on four pathfinding algorithms.


This simulation features cars attempting to move to their goals while avoiding collisions with other cars. 

The variable max_wait determines how long a car waits before it replans its route, while the variable max_stuck determines how long a car has been stuck in one place before that car is timed out. 


The functions for running the simulation and performing single algorithm or multi algorithm analysis are highly customisable, with parameters for everything.


To add realism, obstacles can be chosen which block the movement of cars, leading to unpredictable pathfinding.


In addition, when performing analyses, grid configurations can be seeded to allow for reproducibility of results.


Example of the BFS algorithm running with 50 cars:
<br>
![BFS_Sim](/images/BFS_traffic_sim.gif)


## The Algorithms
### A* 
Combines actual distance with a heuristic estimate of remaining distance to find the optimal path.
<br>
Generally fast and accurate.

### Dijkstra's Algorithm
Explores all routes in order of cumulative cost to guarantee the shortest path. No heuristic guidance.
<br>
Moderate speed but high accuracy.

### Breadth first search
Explores all neighbours to guarantee shortest path by number of steps but ignores cost weighting.
<br>
Slower but high accuracy.

### Greedy best-first search
Rushes toward the goal using only the heuristic estimate.
<br>
Finds paths quickly but no guarantee they are optimal.

## Obstacles
Four obstacles were chosen, these are: <br>
### Random obstacles
Singular obstacles are randomly placed around the grid. <br>
Very little disruption occurs. <br>

### Clusters
Clusters of obstacles are placed around the grid at random, the centre of the cluster is first placed and then the rest of the cluster is randomly generated. <br>
Some moderate disruption usually occurs. <br>

### Walls
Walls are placed along the horizontal and vertical centre of the grid with occasional gaps for cars to move through. <br>
Causes moderate to high disruption. <br>

### Blocks
City blocks are placed onto the grid, with narrow streets for cars to move around. <br>
High disruption occurs. <br>

### Example of the blocks obstacle type.
![AStar_sim_blocks](/images/AStar_obst_traffic_sim.gif)

## Single algorithm analysis
A single algorithm is compared against itself a set amount of times to gather information on how it performs. <br>
The metrics measured are: success rate, average steps to completion, path efficiency, computation time, total replanning events, and total congestion events.

Example of single algorithm analysis performed on the greedy best-first search algorithm.
![Greedy_Analysis](/images/Greedy_trials_visualisation.png)

## Multi algorithm analysis
All four algorithms are tested against each other on the same seeded grid configurations. <br>
The metrics measured are: algorithm failure rates, path efficiency, and computation time.

Example of multi algorithm analysis run across 10 trials with 50 cars.
![Algorithm_comparison](/images/algorithm_comparison.png)

## Dependencies 
- NumPy
- Matplotlib
- Pillow
- Pandas

## How to run
1. Open the notebook in Jupyter.
2. Configure parameters to your liking.
3. Run all cells.
