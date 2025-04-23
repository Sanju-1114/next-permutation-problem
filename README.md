# Next Permutation Problem

## Overview
This repository,contains a C++ solution for **LeetCode Problem 31: Next Permutation**. The program implements an algorithm to find the next lexicographically greater permutation of a given sequence of numbers. If no such permutation exists, it rearranges the sequence to the lowest possible order (i.e., sorted in ascending order).

## Problem Description
Given a sequence of numbers, the task is to rearrange them to form the next lexicographically greater permutation. If the sequence is already the highest possible permutation, rearrange it to the lowest permutation.

### Example
- Input: `nums = [1, 2, 3]`
- Output: `[1, 3, 2]`
- Explanation: The next permutation of `[1, 2, 3]` is `[1, 3, 2]`.

- Input: `nums = [3, 2, 1]`
- Output: `[1, 2, 3]`
- Explanation: `[3, 2, 1]` is the highest permutation, so it is rearranged to the lowest permutation `[1, 2, 3]`.

## Solution Approach
The algorithm follows these steps:
1. **Find the pivot**: Identify the first index `pivot` from the right where `nums[pivot] < nums[pivot+1]`. This indicates the point where the sequence starts decreasing.
   - If no such pivot exists, the sequence is the highest permutation, so reverse the entire array to get the lowest permutation.
2. **Find the next larger element**: From the right, find the smallest element greater than `nums[pivot]` and swap it with `nums[pivot]`.
3. **Reverse the subarray**: Reverse the subarray from `pivot+1` to the end to ensure the smallest possible permutation after the pivot.

### Time Complexity
- **O(n)**: Where `n` is the length of the input array. Each step (finding the pivot, finding the next larger element, and reversing) takes linear time.

### Space Complexity
- **O(1)**: The algorithm modifies the array in-place, using only a constant amount of extra space.

## File Structure
- `next_permutation_problem.cpp`: The C++ source code containing the implementation of the `nextPermutation` function and a `main` function for testing.

## How to Run
1. **Clone the repository**:
   ```bash
   git clone https://github.com/Sanju-1114/next-permutation-problem.git
   ```
2. **Compile the code**:
   ```bash
   g++ next_permutation_problem.cpp -o next_permutation
   ```
3. **Run the executable**:
   ```bash
   ./next_permutation
   ```
4. **Example Output**:
   For the input `nums = [1, 2, 3]`, the output will be:
   ```
   1 3 2
   ```

## Dependencies
- C++ Standard Library ( `<iostream>`, `<vector>`, `<algorithm>` )

## Notes
- The solution uses the `std::vector` for dynamic array handling and `std::swap` for swapping elements.
- The commented-out code in `next_permutation_problem.cpp` shows alternative implementations (e.g., using `std::reverse`) that were replaced with manual reversal for clarity.
