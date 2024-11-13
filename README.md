# LEETCODE-Arrays-2563
## Counting Fair Pairs

**Problem:**
Given an integer array `nums` and two integers `lower` and `upper`, find the number of pairs `(i, j)` such that:

1. `i < j`
2. `lower <= nums[i] + nums[j] <= upper`

**Solution Approach:**

The code utilizes a two-pointer technique and binary search to efficiently count the fair pairs. 

**Code Breakdown:**

1. **`lowerb` and `upperb` functions:**
   - These helper functions are used to perform binary search on the sorted array `nums`.
   - `lowerb` finds the lower bound index of elements greater than or equal to a target value.
   - `upperb` finds the upper bound index of elements less than or equal to a target value.

2. **`countFairPairs` function:**
   - **Sorting:** The array `nums` is sorted to enable efficient binary search.
   - **Iterating over elements:** For each element `nums[i]`, we need to find the number of elements `nums[j]` (where `j > i`) such that `lower <= nums[i] + nums[j] <= upper`.
   - **Binary Search:**
     - We can rephrase the condition as `lower - nums[i] <= nums[j] <= upper - nums[i]`.
     - Using the `lowerb` and `upperb` functions, we can efficiently find the number of elements in the range `[lower - nums[i], upper - nums[i]]`.
     - The difference between the upper and lower bound indices gives the number of valid pairs for the current `i`.
   - **Accumulating the count:** The count of valid pairs for each `i` is added to the `result`.

**Time Complexity:**
- Sorting the array takes O(n log n) time.
- The outer loop iterates `n` times.
- The binary search for each iteration takes O(log n) time.
- Therefore, the overall time complexity is O(n log n).

**Space Complexity:**
- The space complexity is O(1) as we are using constant extra space.

By effectively utilizing binary search to find the number of valid pairs for each element, the code achieves an efficient solution to the given problem.
