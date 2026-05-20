# DP – House Robber II

## What I Did

Solved the House Robber II problem using Dynamic Programming.

Unlike House Robber I, houses are arranged in a circle.

This means:

* first and last houses are adjacent
* both cannot be robbed together

So I divided the problem into two cases:

* skip the last house
* skip the first house

Then I applied House Robber I logic on both cases.

---

## Core Idea

```text
answer = max(
    rob(first → n-1),
    rob(second → n)
)
```

For each case:

```text
dp[i] = max(dp[i-1], dp[i-2] + nums[i])
```

Take maximum money by:

* skipping current house
* robbing current house

---

## Approach (Tabulation)

* Handled base case:

  * if only one house exists → return that value

* Created two arrays:

  * `skipLastHouse`
  * `skipFirstHouse`

* Case 1:

  * Excluded last house
  * Applied House Robber I logic

* Case 2:

  * Excluded first house
  * Applied House Robber I logic

* Returned maximum value from both cases

---

## Key Learning

* Learned how to convert circular problems into linear problems
* Reused previous DP logic using helper function
* Practiced breaking a problem into multiple cases
* Strengthened Pick / Not Pick pattern understanding

---

## My Understanding

Since the first and last houses are connected:

* if I rob the first house → cannot rob last
* if I rob the last house → cannot rob first

So solve both possibilities separately and take the maximum answer.

<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/61c588a2-65fb-4ffc-a0b6-7e05e94439cb" />
<img width="899" height="1599" alt="image" src="https://github.com/user-attachments/assets/ebb34b38-fb08-4a4e-94ff-db760b6172bd" />
