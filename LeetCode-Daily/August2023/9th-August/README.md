### 2616. Minimize the Maximum Difference of Pairs | Link <a href="https://leetcode.com/problems/search-in-rotated-sorted-array/"><img src="https://leetcode.com/_next/static/images/logo-dark-c96c407d175e36c81e236fcfdd682a0b.png" alt="LeetCode Logo" width="18"> </a>

##### What?

> Approach: Binary Search + Greedy Pairing

##### Why?

 - `Binary search` is employed to efficiently narrow down the search space for the `minimum maximum difference`.
 - `Greedy pairing` helps in counting the number of pairs that can be formed within a `certain maximum difference`.

##### How?

> **1. Sort the Array:**

 - The solution starts by sorting the given array nums in ascending order
 - Sorting helps us identify pairs with small differences easily.

> **2. Binary Search:**
 - we start by making a guess for the maximum difference  `mid = (l + r) / 2` and
 - checking how many pairs of numbers can be formed with differences less than or equal  to this guess.

> **3. Greedy Pairing:** (To count no. of pairs)

 - For a given guess of the maximum difference, we iterate through the sorted array and pair up numbers greedily.
 - If the difference between the current number and the previous number is less than or equal to our guess, we count it as a valid pair.
 - This approach ensures that we count as many pairs as possible within the given maximum difference constraint.


> **Based on the count of pairs we get from the greedy pairing, we update the range for our guess:**

- If the count of pairs is greater than or equal to the required number of pairs (p), then we can reduce the maximum difference.
  
  - So, we move the upper limit `r` of the range closer to the current guess `r = mid`.

- Else: if the count of pairs is less than the required number of pairs (p), it means we need a larger maximum difference.
  
  - So, we move the lower limit `l` of the range further from the current guess `l = mid + 1`.


