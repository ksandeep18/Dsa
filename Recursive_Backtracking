
# 🔁 Recursive Backtracking – Theory for Placements

## 🚀 What is Recursive Backtracking?

**Backtracking** is a problem-solving algorithm that uses **recursion** to explore all possible solutions and **backtracks** when it hits a dead end.

> It's used when you need to make **choices** at each step and **revoke those choices** (backtrack) if they don't lead to a valid solution.

## 🧠 Core Idea:
> **Try ➝ Check ➝ Explore ➝ Undo**

1. **Try a decision** (place a number, move a knight, choose a character)  
2. **Check** if it's valid  
3. **Explore** further (recursive call)  
4. If not valid → **Undo** the step (backtrack) and try the next choice  

## 🧩 Where It's Used:

| Problem Type         | Examples                                           |
|----------------------|----------------------------------------------------|
| Combinatorics        | Subsets, permutations, combinations                |
| Constraint problems  | N-Queens, Sudoku, Word Search                      |
| Pathfinding          | Maze solving, Rat in a Maze, Knights Tour          |
| Game problems        | Crossword fill, Crossword puzzle                   |
| String generation    | Palindromic partitions, IP address combinations    |

## ⚙️ Algorithm Template

```python
def backtrack(path, options):
    if is_valid(path):
        result.append(path[:])
        # or return, depending on the problem

    for choice in options:
        if is_safe(choice):        # Optional
            path.append(choice)    # Choose
            backtrack(path, options)  # Explore
            path.pop()             # Un-choose (Backtrack)
```

## 🔑 Key Concepts

### 1. **Recursive Structure**
Backtracking is inherently **recursive** — you dive into deeper levels for each choice.

### 2. **Backtracking Step**
This is the "**undo**" step — when a path fails, you go one level back and try the next alternative.

### 3. **Pruning**
Avoid unnecessary work:
- Skip invalid choices early
- Use constraints to reduce the search space

## ⚡ Time Complexity Insight

Backtracking usually has **exponential time complexity** because it tries all possibilities.

E.g.,
- N-Queens → O(N!)
- Subsets of size N → O(2^N)
- Permutations → O(N!)

But **pruning** and **memoization** can significantly reduce time.

## 🧠 Pattern Recognition: Common Problems

| Pattern               | Problem Examples                        |
|------------------------|------------------------------------------|
| Generate All          | Subsets, combinations, permutations      |
| Decision Tree         | N-Queens, Sudoku, Crossword              |
| Constraint Checks     | Palindrome Partitioning, Expression Add |
| Multi-branch Options  | Maze problems, Word Search               |

## 📘 Tips for Interviews

- Always define:
  - **Base case** → when to stop recursion
  - **Choices** → what decisions can be made at each step
  - **Constraints** → what makes a choice valid or invalid

- Use helper functions with extra parameters (like `path`, `start`, `visited`, etc.)

## ✅ Example: Subsets (Power Set)

```python
def subsets(nums):
    res = []

    def backtrack(start, path):
        res.append(path[:])  # Add current path as a subset
        for i in range(start, len(nums)):
            path.append(nums[i])           # Choose
            backtrack(i + 1, path)         # Explore
            path.pop()                     # Backtrack

    backtrack(0, [])
    return res
```

## 🧩 N-Queens Snippet

```python
def solveNQueens(n):
    res = []
    board = [["."] * n for _ in range(n)]

    def is_safe(r, c):
        for i in range(r):
            if board[i][c] == "Q": return False
            if c - (r - i) >= 0 and board[i][c - (r - i)] == "Q": return False
            if c + (r - i) < n and board[i][c + (r - i)] == "Q": return False
        return True

    def backtrack(r):
        if r == n:
            res.append(["".join(row) for row in board])
            return
        for c in range(n):
            if is_safe(r, c):
                board[r][c] = "Q"
                backtrack(r + 1)
                board[r][c] = "."

    backtrack(0)
    return res
```

## 🔚 Summary

- 📌 **Recursive Backtracking** = Try → Explore → Backtrack  
- 🔁 Used when solution involves **exploring all paths**  
- ✂️ Use **constraints to prune**  
- 🧠 Think in terms of **states and choices**
