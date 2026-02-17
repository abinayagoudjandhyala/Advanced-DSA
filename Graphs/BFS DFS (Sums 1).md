
# Graph Traversal Practice – BFS / DFS (Day Notes)

Today I solved graph problems using **BFS and DFS traversal techniques** on grid-based graphs.

---

## Number of Provinces (547)

### Core Idea

Treat the adjacency matrix as a graph and count how many **connected components** exist.

### Logic

* Each city is a node
* If two cities are connected, they belong to the same province
* Use DFS/BFS to visit all connected cities
* Count how many separate traversals are needed

### Key Learning

* Connected components concept
* Visited array is necessary to avoid revisiting nodes
* Works like DFS on an undirected graph

---

## Rotting Oranges (994)

### Core Idea

Simulate spread using **multi-source BFS**.

### Logic

* All rotten oranges act as starting points
* Spread rot level by level using a queue
* Each BFS layer represents 1 minute
* Count time until all oranges become rotten

### Key Learning

* BFS can simulate time-based spreading
* Multi-source BFS starts from multiple nodes
* Queue size helps track levels (minutes)

---

## Concepts Practiced Today

* BFS traversal on grid
* DFS for connected components
* Multi-source BFS
* Visited tracking
* Graph modeling of matrix problems

---

## Problems Solved Today

* 547 — Number of Provinces
* 994 — Rotting Oranges

<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/31aa629d-9f33-49ca-b93a-049ed833fa90" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/a83146ea-ba12-49cc-ba1f-47e8c46a2985" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/e48512be-79c3-437a-b7b6-5b9f0c931043" />
