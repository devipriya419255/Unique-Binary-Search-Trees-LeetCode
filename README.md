# Unique-Binary-Search-Trees-Counting-LeetCode

"C implementation of LeetCode #96: Unique Binary Search Trees. Uses iterative Dynamic Programming to calculate the number of unique BST structures without building the trees."

## 🧩 LeetCode 96: Unique Binary Search Trees (C Solution)

A mathematical approach to determine the total number of structurally unique BSTs that can be formed with nodes $1$ to $n$.

## 📖 Problem Description

Given an integer $n$, return the number of structurally unique BSTs which have exactly $n$ nodes of unique values from $1$ to $n$.

### Example
- **Input:** `n = 3`
- **Output:** `5`
- **Explanation:** For $n=3$, the possible structures follow the Catalan number $C_3$.

## 🛠️ Technical Approach

The solution utilizes **Dynamic Programming** based on the following logic:
1. **Root Selection**: Any value $j$ (from $1$ to $i$) can be the root.
2. **Subtree Decomposition**:
   - The number of nodes in the **left subtree** is $j - 1$.
   - The number of nodes in the **right subtree** is $i - j$.
3. **Cartesian Product**: The total combinations for a fixed root $j$ is $dp[j-1] \times dp[i-j]$.
4. **Summation**: $dp[i]$ is the sum of combinations for all possible roots $j$.

This sequence is mathematically known as the **Catalan Numbers**.

## 📊 Complexity Analysis

- **Time Complexity:** $O(n^2)$ — Two nested loops to fill the DP table.
- **Space Complexity:** $O(n)$ — To store the DP table of size $n+1$.

## 🚀 How to Run

1. Save the code as `num_trees.c`.
2. Compile using gcc:
   ```bash
   gcc -O3 num_trees.c -o num_trees
