# AI Car Navigation System: Search Algorithms Implementation

## Overview

In this assignment, you will develop a **car navigation system** that finds the most efficient path between cities using classical search algorithms. Your goal is to implement various algorithms from scratch and compare their performance as the car navigates through a map of cities. You will design and implement the graph that represents the map, implement the search algorithms, and evaluate their performance.

The task simulates a **real-world problem** of finding the shortest or most optimal route between cities, akin to a navigation system in your smartphone or GPS. This project is inspired by the well-known Arad to Bucharest problem in AI, but you’ll be working with your own customized graph.

### Deadline
- **Submission Date**: _(Add deadline date here)_

---

## Table of Contents
1. Objectives
2. Project Requirements
3. Search Algorithms to Implement
4. Map Representation
5. Deliverables
6. How to Run the Code
7. Evaluation Criteria
8. Optional Extensions
9. Getting Help

---

## Objectives

By the end of this project, you should be able to:
- Model a map as a graph with cities as nodes and roads as edges.
- Implement various search algorithms from scratch to navigate the graph.
- Understand the differences between uninformed and informed search algorithms.
- Analyze the performance of different algorithms in terms of time, cost, and path optimality.

---

## Project Requirements

### 1. **Graph Representation**
You will represent the map as a **graph**:
- **Nodes (Vertices)**: Represent cities.
- **Edges**: Represent roads between cities, with associated costs (e.g., distance in kilometers or travel time in hours).
- Your graph should support directed and undirected edges, depending on how the roads are defined.
- Use the map inside the book to define cities and roads.

### 2. **Algorithms**
You will implement **six search algorithms** to help the car find the most optimal path from a starting city to the destination city. These are:
- **Breadth-First Search (BFS)**
- **Depth-First Search (DFS)**
- **Uniform Cost Search (UCS)**
- **Depth-Limited Search (DLS)**
- **A*** (A-star)
- **Recursive Best-First Search (RBFS)**

Each algorithm must be written from scratch. You are not allowed to use external libraries for search algorithms (e.g., `networkx` or `scipy` for pathfinding).

### 3. **Heuristics**
For the informed search algorithms (A* and RBFS), you will need to implement a **heuristic function**. A common heuristic is the **straight-line distance** between two cities, but you can experiment with different heuristics if you'd like.

### 4. **Performance Metrics**
You will compare the performance of the algorithms using:
- **Path cost**: The total cost (e.g., distance or time) for the path found.
- **Time taken**: How long each algorithm takes to find the solution.
- **Nodes explored**: How many cities (nodes) were explored before finding the solution.

---

## Search Algorithms to Implement

### 1. Breadth-First Search (BFS)
- **Type**: Uninformed
- **Behavior**: Explores all neighbors of a city (node) before moving to the next level of the graph. This ensures the shortest path in terms of the number of cities visited, but it doesn't account for varying road lengths or travel times.

### 2. Depth-First Search (DFS)
- **Type**: Uninformed
- **Behavior**: Explores as deeply as possible in one branch before backtracking. It’s not optimal for finding the shortest path but is useful in certain scenarios like exploring mazes.

### 3. Uniform Cost Search (UCS)
- **Type**: Uninformed
- **Behavior**: Expands the least costly node first (based on distance or time). This ensures the shortest path in terms of total cost but can be slow if there are many equally short paths.

### 4. Depth-Limited Search (DLS)
- **Type**: Uninformed
- **Behavior**: DFS but with a set depth limit, useful when the depth of the solution is known or to avoid infinite recursion.

### 5. A* Search
- **Type**: Informed
- **Behavior**: Uses a heuristic to estimate the cost from a city to the goal. A* combines the benefits of UCS with informed guessing, making it both optimal and efficient when the heuristic is well-designed.

### 6. Recursive Best-First Search (RBFS)
- **Type**: Informed
- **Behavior**: A memory-efficient variant of A* that also uses a heuristic but explores paths in a recursive depth-first manner while keeping track of the best alternative path available.

---

## Map Representation

You will represent the map using a graph. Here’s a sample of how your map data could be structured:

### Example Map:
```
Cities: Arad, Sibiu, Fagaras, Bucharest, Timisoara, Rimnicu Vilcea, Craiova, Pitesti
Edges (roads with distances in km):
Arad -> Sibiu: 140 km
Sibiu -> Fagaras: 99 km
Fagaras -> Bucharest: 211 km
Timisoara -> Arad: 118 km
...
```

### Python Data Structure
You may represent the map using an adjacency list or adjacency matrix. For example:

```python
# Adjacency list representation
graph = {
    'Arad': [('Sibiu', 140), ('Timisoara', 118)],
    'Sibiu': [('Arad', 140), ('Fagaras', 99)],
    'Fagaras': [('Sibiu', 99), ('Bucharest', 211)],
    ...
}
```

---

## Deliverables

By the end of the assignment, you must submit:
1. **Code**: Implementations of all six search algorithms, plus the map representation and heuristic functions.
2. **Report**: A brief report comparing the performance of each algorithm on different paths. This should include:
   - How each algorithm performed (time, cost, nodes explored).
   - Which algorithm was the most optimal and why.
   - Observations on the effectiveness of your heuristics (for A* and RBFS).
3. **Visualization (optional)**: You may include a simple visualization of the graph and the path taken by each algorithm using libraries like `networkx` or `matplotlib`.

---

## How to Run the Code

1. **Clone this repository**:
   ```bash
   git clone https://github.com/yourusername/car-navigation-system.git
   cd car-navigation-system
   ```

2. **Run the main program**:
   ```bash
   python main.py
   ```

3. The program will ask for the following inputs:
   - Starting city.
   - Target city.
   - The search algorithm to use.

4. The program will then output:
   - The path taken by the car.
   - The total cost (e.g., distance or time).
   - The number of nodes explored.
   - Time taken by the algorithm.

---

## Evaluation Criteria

| Criterion                 | Description                                                                 | Weight |
|---------------------------|-----------------------------------------------------------------------------|--------|
| **Correctness**            | Does the code implement the search algorithms correctly?                    | 50%    |
| **Heuristics**             | Are the heuristics well-designed and appropriate for the problem?            | 20%    |
| **Code Structure & Style** | Is the code well-organized, modular, and documented?                        | 15%    |
| **Report Quality**         | Does the report clearly explain the results and comparison of algorithms?    | 15%    |


---

## Optional Extensions

If you want to challenge yourself further, consider adding one or more of these optional features:
- **Multiple Objectives**: Implement multi-objective search (e.g., minimize both distance and fuel consumption).
- **Dynamic Road Conditions**: Simulate roadblocks or changes in traffic and adapt your search dynamically.
- **Map Visualization**: Visualize the graph of cities and paths using `networkx` or `matplotlib`.

---

## Getting Help

If you encounter any issues with the assignment or need clarification, feel free to Ask your questions from TAs

---

Good luck with your assignment, and have fun building your AI car navigation system! 🚗💡
