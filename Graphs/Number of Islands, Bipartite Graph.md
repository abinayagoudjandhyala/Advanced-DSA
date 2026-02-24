

# Graph Practice – Islands, Bipartite Check & Directed Cycle Detection (Day Notes)

Today I solved problems involving **connected components in grids**, **graph coloring**, and **cycle detection in directed graphs**.

---

## Number of Islands (200)

### Core Idea

Count how many separate land regions (islands) exist in a grid.

### Logic

* Treat each cell as a node in a graph
* When land (`'1'`) is found, run DFS/BFS to mark the entire connected region as visited
* Each new traversal represents one island

### Key Learning

* Classic connected components problem in grid graphs
* Visiting once prevents recounting
* Grid traversal can be solved using DFS or BFS

---

## Bipartite Graph Check

### Core Idea

Check whether the graph can be divided into two groups such that no adjacent nodes share the same color.

### Logic

* Assign alternating colors while traversing (using BFS/DFS)
* If a neighbor already has the same color → graph is not bipartite
* If coloring succeeds → graph is bipartite

### Key Learning

* Bipartite graphs use **2-coloring logic**
* Helps detect odd-length cycles
* Very common in graph validation problems

---

## Cycle Detection in Directed Graph

### Core Idea

Detect cycles using DFS and a recursion (path) tracking mechanism.

### Logic

* Maintain two arrays:

  * `visited` → nodes already processed
  * `pathVisited` (or recursion stack) → nodes in the current DFS path
* If we revisit a node already in the current path → cycle exists

### Key Learning

* Directed cycle detection differs from undirected case
* Parent tracking is not used; recursion stack is required
* Important for dependency problems like Course Schedule

---

## Concepts Practiced Today

* Connected components in grid graphs
* Graph coloring technique
* DFS-based cycle detection
* Handling directed vs undirected differences

---

## Problems Solved Today

* 200 — Number of Islands
* Bipartite Graph Check
* Cycle Detection in Directed Graph

<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/1c59d9fa-44ff-4e76-81ee-8cc261bcb759" />
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/967c06c4-1940-48a1-a169-0a2745b0643d" />
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/88fd3e9c-4699-421c-bdb9-17f8077da157" />
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/94514223-c2fc-495b-8ff9-e6c62919116d" />
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/d29e899f-1696-4440-808d-07b4205fd616" />
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/e8ec0841-be99-4192-aadd-a1c865fa4197" />
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/4cfe3431-3f5e-4fc6-b206-1801a84d6911" />
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/d678feb5-8a95-4b25-98df-1ae96757555f" />
