# Leetcode_Day80
# Day 80: Subarray Sum Equals K

**LeetCode Problem:** 560. Subarray Sum Equals K  
**Difficulty:** Medium  
**Language:** Java  
**Topics:** Arrays, Prefix Sum, Nested Loops

## Problem Statement

Given an integer array `nums` and an integer `k`, return the total number of contiguous, non-empty subarrays whose sum equals `k`.

A subarray is a continuous sequence of elements taken from an array.

## Approach: Brute Force

I used two nested loops to find all possible subarrays and calculate their sums.

1. Initialize a counter `count` to zero.
2. Use the outer loop to select the starting index of a subarray.
3. Initialize `sum = 0` for each starting index.
4. Use the inner loop to extend the subarray one element at a time.
5. Add each element to `sum`.
6. Whenever `sum == k`, increment `count`.
7. Return `count` after checking all possible subarrays.

This approach checks every possible contiguous subarray and counts those whose sum equals `k`.

## Java Solution

```java
class Solution {
    public int subarraySum(int[] nums, int k) {
        int count = 0;

        for (int i = 0; i < nums.length; i++) {
            int sum = 0;

            for (int j = i; j < nums.length; j++) {
                sum += nums[j];

                if (sum == k) {
                    count++;
                }
            }
        }

        return count;
    }
}

```
Example
Input:
nums = [1, 1, 1], k = 2

Output:
2

Explanation:

The subarrays whose sum equals 2 are:
- [1, 1] at indices 0 and 1.
- [1, 1] at indices 1 and 2.
Therefore, the answer is 2.
Complexity Analysis
- Time Complexity: O(n²), because two nested loops examine all possible subarrays.
- Space Complexity: O(1), because only a few extra variables are used.
Here, n represents the length of the array.
What I Learned
- How to generate all possible contiguous subarrays.
- How to calculate subarray sums efficiently by maintaining a running sum.
- Why every starting index must be considered.
- How nested loops can solve a problem by checking all possible combinations.
Takeaway
A straightforward solution helps build a strong understanding of a problem before exploring more optimized techniques.

Day 80 complete! One more problem solved, one more step forward in my DSA journey.
