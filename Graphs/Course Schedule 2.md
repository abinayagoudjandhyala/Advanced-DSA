# Graph Practice – Topological Sort & Course Schedule II (Day Notes)

Today I worked on problems involving **topological sorting of directed graphs** and **finding a valid ordering of tasks with dependencies**.

---

## Topological Sort (Kahn’s Algorithm)

### Core Idea

Topological sorting is used to find a **linear ordering of nodes** in a **directed acyclic graph (DAG)** such that for every directed edge `u → v`, `u` comes before `v`.

### Logic

* Build adjacency list to represent graph
* Maintain an **in-degree array** for each node
* Add all nodes with `in-degree = 0` to queue
* Perform BFS:
  * Remove node from queue
  * Add it to result
  * Reduce in-degree of neighbors
  * If neighbor becomes 0 → add to queue
* Continue until queue is empty

### Key Learning

* Nodes with `in-degree = 0` are starting points
* Removing edges reduces dependencies
* BFS ensures correct ordering
* If all nodes are processed → valid topological order exists

---

## Course Schedule II (LeetCode 210)

### Core Idea

Return a valid order of courses using **topological sorting**.

### Logic

* Convert prerequisites into graph:
  * `b → a` (to take `a`, you must complete `b`)
* Apply **Kahn’s Algorithm**
* Store nodes in result array
* If result size == number of courses → return order
* Else → cycle exists → return empty array

### Key Learning

* Course scheduling is a direct application of topological sort
* If graph has a cycle → no valid ordering exists
* Order is built dynamically during BFS traversal
* Important to track processed node count

---

## Concepts Practiced Today

* Topological sorting using BFS (Kahn’s Algorithm)
* In-degree based graph processing
* Directed graph modeling
* Dependency resolution problems
* Cycle detection using node count

---

## Problems Solved Today

* 210 — Course Schedule II

