# DP – Unique Paths II

## What I Did

Solved the Unique Paths II problem using 2D Dynamic Programming.

The robot starts from the top-left corner and needs to reach the bottom-right corner.

At each position, I can move only:

* right
* down

Some cells contain obstacles, so the robot cannot pass through them.

---

## Core Idea

```text
dp[i][j] = dp[i-1][j] + dp[i][j-1]
```

But:

```text
If obstacle exists:
dp[i][j] = 0
```

If a cell has an obstacle, no path can pass through it.

---

## Approach (Tabulation)

* Created a 2D dp array
* Handled obstacle cells:

  * If obstacle exists → set value to 0

* Set starting position:

  * `dp[0][0] = 1`

* For remaining cells:

  * Take paths from top
  * Take paths from left
  * Add both values

---

## Key Learning

* Learned how to handle constraints in DP
* Understood modifying recurrence relations
* Practiced using boundary checks
* Strengthened 2D DP concepts

---

## My Understanding

To reach any cell:

* I can come from top
* I can come from left

But if an obstacle exists:

* that cell becomes unreachable

So its number of paths becomes 0.


# DP – Minimum Path Sum

## What I Did

Solved the Minimum Path Sum problem using 2D Dynamic Programming.

The goal is to find the minimum cost path from top-left to bottom-right.

At each position, I can move only:

* right
* down

---

## Core Idea

```text
dp[i][j] = grid[i][j] + min(dp[i-1][j], dp[i][j-1])
```

Minimum cost to reach a cell equals:

* current cell value
* minimum value from top or left

---

## Approach (Tabulation)

* Updated first row:

  * Add previous left values

* Updated first column:

  * Add previous top values

* Used nested loops for remaining cells

* Added current value with minimum of:

  * top value
  * left value

* Returned bottom-right cell value

---

## Key Learning

* Learned optimization using in-place DP
* Understood minimizing instead of counting paths
* Practiced using previous states efficiently
* Strengthened 2D DP thinking

---

## My Understanding

To reach a cell:

* I can come from top
* I can come from left

Choose the path with smaller cost and add the current cell value.
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/b84fa174-f268-42f8-a695-ffbb5afbc393" />
