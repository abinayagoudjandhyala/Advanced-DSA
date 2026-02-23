

# Graph Practice – Shortest Path using BFS (Day Notes)

Today I solved a problem based on **shortest transformation path using BFS**.

---

## Word Ladder (127)

### Core Idea

Find the shortest sequence to transform one word into another by changing one letter at a time.

### Logic

* Treat each word as a node in a graph
* Two words are connected if they differ by one character
* Use BFS to explore transformations
* Each BFS level represents one transformation step
* Stop when the target word is reached

### Key Learning

* BFS guarantees shortest path in unweighted graphs
* Words can act as graph states
* Use a set to avoid revisiting words

---

## Concepts Practiced Today

* BFS for shortest path
* Implicit graph construction
* State transformation problems
* Level-based traversal

---

## Problem Solved Today

* 127 — Word Ladder

<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/1d7e8523-6934-4c59-b533-dd3f31bc98c0" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/77c9c7cc-acbf-4b5e-bf93-f617d0e5e79e" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/60159f16-41c0-4158-b80d-5c13d2047d84" />
