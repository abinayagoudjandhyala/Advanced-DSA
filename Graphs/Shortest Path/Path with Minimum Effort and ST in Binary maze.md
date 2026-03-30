# Graph Practice – Grid BFS & Dijkstra (Day Notes)

Today I solved problems involving **shortest path in grids** using both **BFS and Dijkstra’s Algorithm**, including 4-direction and 8-direction movement.

---

## Shortest Path in Binary Matrix (8 Directions)

### Core Idea

Use **BFS** to find the shortest path in a grid where movement is allowed in **8 directions**.

---

### Logic

* Each cell is treated as a node
* Move in 8 directions (including diagonals)
* Use BFS:
  * Start from (0,0)
  * Track path length
  * Visit valid neighbors (within bounds and not blocked)
* First time reaching destination = shortest path

---

### Key Learning

* BFS guarantees shortest path in unweighted grid
* 8-direction traversal requires careful boundary checks
* Grid can be used as visited array

---

## Shortest Distance in Binary Maze (4 Directions)

### Core Idea

Use **BFS** to find shortest distance when movement is allowed in **4 directions**.

---

### Logic

* Convert grid into graph
* Move in 4 directions (up, down, left, right)
* Maintain distance array
* Use BFS to update distances
* Stop when destination is reached

---

### Key Learning

* BFS works when all moves have equal cost
* Distance increases level by level
* Useful for maze and grid traversal problems

---

## Path With Minimum Effort (Dijkstra)

### Core Idea

Use **Dijkstra’s Algorithm** to minimize the **maximum effort** between adjacent cells.

---

### Logic

* Use a **priority queue (min-heap)**
* Each state stores:
  * row, col, current effort
* Move in 4 directions
* Effort = max(current effort, height difference)
* Always process cell with minimum effort

---

### Key Learning

* Not all shortest path problems use BFS
* Dijkstra handles weighted paths
* Can optimize based on custom cost (max difference)

---

## Concepts Practiced Today

* BFS in grid (4-direction & 8-direction)
* Dijkstra in grid
* Priority Queue usage
* Difference between BFS and Dijkstra
* Grid → Graph conversion

---

## Problems Solved Today

* Shortest Path in Binary Matrix (8 directions)
* Shortest Distance in Binary Maze (4 directions)
* Path With Minimum Effort

---

## 📈 What I Improved Today

* Understood difference between BFS and Dijkstra clearly
* Improved confidence in grid-based problems
* Learned handling multiple directions efficiently
* Strengthened problem-solving for medium-level graphs

---
![WhatsApp Image 2026-03-30 at 9 26 18 PM](https://github.com/user-attachments/assets/7423c31d-4ef4-4f2b-9fcc-5915d764a2f6)
![WhatsApp Image 2026-03-30 at 9 26 24 PM](https://github.com/user-attachments/assets/68927206-5057-4cb6-8a5f-e5603e5de5f5)
![WhatsApp Image 2026-03-30 at 9 26 31 PM](https://github.com/user-attachments/assets/ac811f3e-7f84-42b0-8202-117a4aac1789)


