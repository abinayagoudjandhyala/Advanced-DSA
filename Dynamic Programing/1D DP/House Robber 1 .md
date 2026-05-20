# DP – House Robber I

## What I Did

Solved the House Robber I problem using Dynamic Programming.

For each house, I have two choices:

* Rob the current house
* Skip the current house

If I rob the current house:

* I cannot rob the previous house

---

## Core Idea

```text
dp[i] = max(dp[i-2] + nums[i], dp[i-1])
```

Maximum money at house `i` is:

* Rob current house → `dp[i-2] + nums[i]`
* Skip current house → `dp[i-1]`

Take the maximum of both choices.

---

## Approach (Tabulation)

* Created a dp array
* Set base cases:

  * `dp[0] = nums[0]`
  * `dp[1] = max(nums[0], nums[1])`

* Used a loop from index `2` to `n-1`

* For each house:

  * Calculate profit if robbed
  * Calculate profit if skipped
  * Store maximum value in dp array

---

## Key Learning

* Learned Pick / Not Pick DP pattern
* Understood how previous states help solve the current state
* Practiced tabulation (bottom-up DP)
* Learned optimization is possible from `O(n)` space to `O(1)`

---

## My Understanding

For every house, I decide:

* Rob it and add money from `i-2`
* Skip it and take previous profit

Then take whichever gives maximum money.

<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/126bf5f0-3c44-4a5e-afec-910f9df8f858" />
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/09a52b94-0801-4c2d-8303-a4bff4f9c51d" />

