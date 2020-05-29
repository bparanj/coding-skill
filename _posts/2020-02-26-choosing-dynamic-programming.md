---
layout: post
title: Dynamic Programming Q&A
excerpt: What are the conditions to choose dynamic programming? In Dynamic Programming how to characterize structure of optimal solution?
---

## What are the conditions to choose dynamic programming?

If the following conditions are met, then we can choose Dynamic Programming to solve that problem:

- Recursion - Problem can be solved using the recursive function calls.
- Optimization (min, max, largest) - The problem is requiring some optimizations such as finding Longest Common Sub sequence.
- Choice is given (option to choose something)
- Overlapping subproblems - The solution of one sub problem can be used to find the solution of another subproblem.
- Likely when two recursive calls are made

## In Dynamic Programming how to characterize structure of optimal solution?
 
1. The characterization of optimal solution is given by the optimal substructure of the problem.
2. Optimal substructure of the problem in dynamic programming is the art of the whole problem where the solution of such part will be latter used to find the solution of the whole problem.
3. The subprograms for the optimal solution will be created as such that solution of all those subproblem can be combined to form the whole big solution.
4. Consider the example of find the subset of numbers in a sequence of number such that their sum will be equal to the given below:
5. This problem is dynamic problem where we can divide the problem into subproblems.
6. Each subproblem will be related to either include a particular number in the while sum or not.
7. The solution of this if problem is given by a recursive equation is shown below:

```
isSubsetSum (set, n, sum) = isSubsetSum (set, n-1, sum) || isSubsetSum (set, n-1, sum-set[n-1])
```

where `isSubsetSum (set, n, sum)` will tell that whether the nth number in the sequence will be included in set to which eventually gives the value equal to sum.

Can I use bottom up Dynamic Programming with iterative solution as well as recursive solution? Is bottom up Dynamic Programming used only with iterative solution?

No, you cannot use bottom up Dynamic Programming with iterative solution as well as recursive solution.
Yes, bottom up Dynamic Programming is used only with iterative solution.
Bottom up dynamic programming works with memoization and iterative approach. 
For recursive solution, we have to solve the problem top down approach which is also an expensive choice in terms of complexity and stack memory issues.
However, it depends upon the type of the problem, dynamic programming can be used by top-down recursive solution and bottom up iterative solution.

## Bottom Up Dynamic Programming Algorithm

For example, here is the solution for Fibonacci from MIT class notes:

```python
 fib = {}
 for k in range(1:n+1):
   if k <=2: f = 1
   else: f = fib[k-1] + fib[k-2]
   fib[k] = f
 return fib[n]
```
 