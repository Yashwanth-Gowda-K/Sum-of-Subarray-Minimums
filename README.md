# Sum-of-Subarray-Minimums

Given an array of integers, the goal is to find the **sum of the minimum value of every possible subarray**.  
Since the answer can be very large, return it modulo `10^9 + 7`.

---

## 💡 Approach

Brute force gives TLE for large inputs, so we use a **monotonic stack** to efficiently compute:

- `prev_less[i]`: Number of consecutive elements to the left that are **greater than** `arr[i]`.
- `next_less[i]`: Number of consecutive elements to the right that are **greater than or equal to** `arr[i]`.

The total contribution of `arr[i]` to the result is:  
arr[i] * prev_less[i] * next_less[i]
