
# DP – Climbing Stairs

## What I Did

Solved the Climbing Stairs problem using Dynamic Programming.

At each step, I can:

* take 1 step
* take 2 steps

To reach step `n`, I can come from:

* `n-1`
* `n-2`

---

## Core Idea

```
dp[i] = dp[i-1] + dp[i-2]
```

Number of ways to reach step `i` is the sum of ways to reach the previous two steps.

---

## Approach (Tabulation)

* Created a dp array
* Set base cases:

  * `dp[0] = 1`
  * `dp[1] = 1`
* Used a loop from 2 to n to fill the dp array

---

## Key Learning

* This problem follows a Fibonacci pattern
* Learned how to form a recurrence relation
* Practiced tabulation (bottom-up DP)

---

## My Understanding

To reach a step, add the ways of the last two steps.

<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/d278c44b-1726-4ce7-93c2-212258978aaf" />
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/70c31e8b-b0ce-4516-b4f1-7dd4a74fc23a" />
