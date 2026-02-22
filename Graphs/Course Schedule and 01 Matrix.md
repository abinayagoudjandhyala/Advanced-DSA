
# Graph Practice – Cycle Detection, Topological Sort & Matrix Distance (Day Notes)

Today I solved problems involving **cycle detection in graphs**, **course scheduling using topological sort**, and **distance computation in a grid**.

---

## Detect Cycle in Undirected Graph

### Core Idea

Use BFS/DFS traversal and track the **parent node** to detect cycles.

### Logic

* Traverse graph using BFS
* Store `(node, parent)` while visiting
* If a visited neighbor is found that is not the parent → cycle exists

### Key Learning

* Parent tracking is essential in undirected graphs
* Visited node alone does not indicate a cycle
* Works as connected-component traversal with validation

---

## Course Schedule (Topological Sort – Kahn’s Algorithm)

### Core Idea

Check if all courses can be completed by detecting cycles in a **directed graph**.

### Logic

* Build adjacency list from prerequisites
* Compute indegree of each node
* Start BFS from nodes with indegree = 0
* Reduce indegrees as edges are removed
* If all nodes are processed → no cycle

### Key Learning

* Topological sorting detects cycles in directed graphs
* If some nodes never reach indegree 0 → cycle exists
* BFS-based topological sort is called **Kahn’s Algorithm**

---

## 01 Matrix (542)

### Core Idea

Find distance of each cell to the nearest `0`.

### Logic

* Use two-pass DP (or multi-source BFS alternative)
* First pass checks top and left neighbors
* Second pass checks bottom and right neighbors
* Gradually relax distances to nearest zero

### Key Learning

* Grid problems can be solved using BFS or DP relaxation
* Distance propagation is similar to shortest path updates
* Directional sweeps ensure all possibilities are considered

---

## Concepts Practiced Today

* Cycle detection in undirected graphs
* Topological sort (directed graph processing)
* BFS-style dependency resolution
* Grid distance computation
* Graph modeling of matrices

---

## Problems Solved Today

* Detect Cycle in Undirected Graph
* 207 — Course Schedule
* 542 — 01 Matrix
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/eaf7dd43-e37e-42f3-b091-1e5014986728" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/0ffcc669-c1c3-4256-b2e3-78af00b31498" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/8e31e76a-f56d-4aa2-91aa-f44864d60dea" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/dd1003bd-fd39-4e30-8b55-a55fd91387a5" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/31c9b831-681a-4d68-a963-8fb1e08ddb8f" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/29afa4b5-b243-4627-af8a-6087edd0aaae" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/cf670812-a11d-4f74-8745-dff7d19bce03" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/6438590b-d5f2-4e51-b6a7-54e97c1db02c" />


