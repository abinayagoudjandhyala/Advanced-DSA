
# Graphs – Fundamentals, BFS & DFS (Theory Notes)

Today I started learning **Graph concepts** and covered the basics along with **BFS and DFS traversal**.

---

## What Is a Graph?

A graph is a collection of:

* **Vertices (Nodes)**
* **Edges (Connections between nodes)**

Used to represent relationships like networks, maps, and connections.

---

## Types of Graphs

* **Undirected Graph** → edges work both ways
* **Directed Graph** → edges have direction
* **Weighted Graph** → edges have cost/weight
* **Unweighted Graph** → edges have no cost

---

## Graph Representation

Graphs can be stored using:

* Adjacency Matrix
* Adjacency List (more commonly used)

---

## Breadth First Search (BFS)

### Core Idea

Visit nodes **level by level** starting from a source node.

### How It Works

* Use a **queue**
* Visit neighbors first before going deeper
* Mark nodes as visited to avoid repetition

### When Used

* Shortest path in unweighted graphs
* Level-wise traversal
* Finding minimum steps

---

## Depth First Search (DFS)

### Core Idea

Go **deep into a path** before exploring other paths.

### How It Works

* Use **recursion or stack**
* Explore one branch fully
* Backtrack when no further nodes exist

### When Used

* Path existence problems
* Cycle detection
* Connected components

---

## BFS vs DFS (Conceptual View)

| BFS                    | DFS                  |
| ---------------------- | -------------------- |
| Level-wise traversal   | Deep traversal       |
| Uses Queue             | Uses Recursion/Stack |
| Good for shortest path | Good for exploration |

---

## Key Learning Today

* Graph traversal is similar to tree traversal but must handle cycles
* Need a **visited array/set** to avoid revisiting nodes
* BFS and DFS are foundational for all graph algorithms

---

## Topics Covered Today

* Graph Basics
* Graph Representation (overview)
* BFS Traversal (theory)
* DFS Traversal (theory)

<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/de63c5ee-4914-4611-aabf-03acec61de9a" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/93565a14-a8b4-429c-aefb-93ef30748897" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/f335f95b-6c57-4213-9fc2-bf148999616c" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/0aaf8b35-4874-43dc-a1ec-f2d370094265" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/9160d1cf-583b-471a-a818-9aa0a304c247" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/560740e2-1e62-4416-9361-69822cd3883b" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/7dd9b4c1-32c4-4ccc-933d-be55766cbbfd" />


