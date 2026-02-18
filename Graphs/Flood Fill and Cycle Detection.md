
# Graph Traversal Practice – Flood Fill & Cycle Detection using BFS (Day Notes)

Today I practiced applying **BFS traversal** to solve region-based problems and detect cycles in graphs.

---

## Flood Fill

### Core Idea

Treat the grid as a graph and change the color of all connected cells starting from a source.

### Logic

* Each cell acts like a node
* Move in 4 directions (up, down, left, right)
* Only visit cells with the same initial color
* Use BFS/DFS to traverse the connected component
* Update color while visiting

### Key Learning

* Grid problems can be modeled as graphs
* Need boundary checks and visited handling
* Traversal spreads like exploring a connected component

---

## Detect Cycle in Undirected Graph (Using BFS)

### Core Idea

While traversing using BFS, if we reach a visited node that is **not the parent**, a cycle exists.

### Logic

* Use a queue storing `(node, parent)`
* Mark nodes as visited during traversal
* For each neighbor:

  * If not visited → continue BFS
  * If visited and not the parent → cycle detected

### Key Learning

* Parent tracking is essential in undirected graphs
* Simply seeing a visited node does not mean a cycle
* BFS can be used not just for traversal but also structure validation

---

## Concepts Practiced Today

* BFS traversal on grid and graph
* Connected component exploration
* Parent-based cycle detection
* Modeling matrix problems as graphs

---

## Problems Practiced Today

* Flood Fill
* Cycle Detection using BFS

<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/fb0fc0ee-7d20-462a-aa96-45650aa22256" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/79c068c7-9e9a-4b88-ae1d-5ca9f0054586" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/c952d33f-7577-404c-a3dc-30eca29e8a1d" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/23929329-484a-4a94-90d4-317206f90557" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/5b7a73bd-552f-4498-a8fd-553c460e25ab" />
