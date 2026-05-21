# DP – Unique Paths

## What I Did

Solved the Unique Paths problem using 2D Dynamic Programming.

The robot starts from the top-left corner and needs to reach the bottom-right corner.

At each position, I can move only:

* right
* down

---

## Core Idea

```text
dp[i][j] = dp[i-1][j] + dp[i][j-1]
```

Number of ways to reach a cell is:

* ways from the top cell
* ways from the left cell

Add both to get total paths.

---

## Approach (Tabulation)

* Created a 2D dp array (`grid`)
* Filled the first row and first column with `1`

Reason:

* For first row → only right movement possible
* For first column → only downward movement possible

* Used nested loops for remaining cells
* Applied recurrence relation

---

## Key Learning

* Learned how to solve problems using 2D Dynamic Programming
* Practiced identifying movement directions
* Understood how each state depends on previous states
* Strengthened tabulation (bottom-up DP)

---

## My Understanding

To reach any cell:

* I can come from above
* I can come from the left

So total paths for that cell are the sum of both paths.
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/873c28cf-3604-4899-9385-250d15dd4d81" />

