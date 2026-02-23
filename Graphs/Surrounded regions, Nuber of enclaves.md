
# Graph Practice – Boundary Traversal Problems (Day Notes)

Today I solved problems based on **boundary DFS/BFS traversal** where we identify regions connected to the edges of the grid.

---

## Surrounded Regions (130)

### Core Idea

Capture `'O'` regions that are completely surrounded by `'X'`.

### Logic

* Start traversal from **boundary `'O'` cells**
* Mark all connected `'O'` cells as safe
* These boundary-connected regions cannot be captured
* Convert remaining `'O'` → `'X'`
* Restore safe cells back to `'O'`

### Key Learning

* Always think from boundary instead of checking each region
* Boundary-connected components remain unchanged
* Reverse traversal simplifies region problems

---

## Number of Enclaves (1020)

### Core Idea

Count land cells that cannot reach the boundary.

### Logic

* Run DFS/BFS from boundary land cells
* Remove all reachable land from the boundary
* Remaining land cells are enclaves

### Key Learning

* Same pattern as Surrounded Regions
* Eliminate boundary-connected land first
* Then count remaining cells

---

## Concepts Practiced Today

* Grid traversal using DFS/BFS
* Boundary-based graph thinking
* Connected component removal
* Matrix as graph modeling

---

## Problems Solved Today

* 130 — Surrounded Regions
* 1020 — Number of Enclaves

<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/9f47846d-12c4-4766-96ca-2b1651989d4a" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/da2b4385-56e1-48dc-b765-4eb556c15e07" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/2f9842a0-65bf-4201-98b6-dca7e7b02d20" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/3a746b75-e8b3-4d7b-b10d-1603f86a4efc" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/6ea3ffdb-9593-4ba4-9e0f-4a7e12577ba0" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/3814aa94-b419-44fa-8b21-bc7f0e0236f9" />

