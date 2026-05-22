# DP – Triangle (Minimum Path Sum in Triangle)

## What I Did

Solved the Triangle problem using Dynamic Programming.

The goal is to find the minimum path sum from the top of the triangle to the bottom.

At each position, I can move only to:

* directly below
* diagonally below-right

---

## Core Idea

```text
dp[level][i] = triangle[level][i] + 
               min(dp[level+1][i], dp[level+1][i+1])
```

Minimum path at a position equals:

* current value
* minimum of the two possible paths below

---

## Approach (Bottom-Up Tabulation)

* Created a dp array
* Started from the last level and moved upward
* For every position:

  * Take current value
  * Add minimum value from:

    * below element
    * diagonal element

* Continue until reaching the top

* Return `dp[0][0]`

---

## Key Learning

* Learned Bottom-Up Dynamic Programming
* Understood solving problems from destination to source
* Practiced choosing minimum among multiple paths
* Strengthened 2D DP concepts

---

## My Understanding

For every position in the triangle:

* I have two choices:
  * move down
  * move diagonal-right

Choose the smaller path and add the current value.

By calculating from bottom to top, I already know the minimum values needed for future decisions.
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/352aaaed-5669-4f20-8d23-d774930dfc34" />
