---
layout: post
title: Dynamic Programming
excerpt: Dynamic Programming is an algorithm design method that can be used when the solution to a problem may be viewed as the result of a sequence of decisions. Some examples are Knapsack, Optimal Merge Patterns and Shortest Path.
---

Dynamic Programming is an algorithm design method that can be used when the solution to a problem may be viewed as the result of a sequence of decisions. Some examples are Knapsack, Optimal Merge Patterns and Shortest Path.
 
For some of the problems that may be viewed in this way, an optimal sequence of decisions may be found by making the decisions one at a time and never making an erroneous decision. 

This is true for all problems solvable by the greedy method. For many other problems, it is not possible to make stepwise decisions (based only on local information) in such a manner that the sequence of decisions made is optimal. 

One way to solve problems for which it is not possible to make a sequence of stepwise decisions leading to an optimal decision sequence is to try out all possible decision sequences. We could enumerate all decision sequences and then pick out the best. 

<blockquote class="note">
  <strong>TIP</strong> 
  <p>
    Dynamic programming often drastically reduces the amount of enumeration by avoiding the enumeration of some decision sequences that cannot possibly be optimal. 
  </p>
</blockquote>

### Principle of Optimality

In dynamic programming the optimal sequence of decisions is arrived at by making explicit appeal to the _Principle of Optimality_. 

This principle states that an optimal sequence of decisions has the property that whatever the initial state and decision are, the remaining decisions must constitute an optimal decision sequence with regard to the state resulting from the first decision. 

### Greedy Method vs Dynamic Programming

Thus, the essential difference between the greedy method and dynamic programming is that in the greedy method only one decision sequence is ever generated. In dynamic programming, many decision sequences may be generated. However, sequences containing suboptimal subsequences cannot be optimal (if the principle of optimality holds) and so will not be generated.

An important feature of the dynamic programming approach is that optimal solutions to subproblems are retained so as to avoid recomputing their values. The use of these tabulated values makes it natural to recast the recursive equations into an iterative program. 

### Is Dynamic Programming Applicable?

Ask yourself the following questions:

1. Is it possible to divide the problem into subproblems of the same type?

2. Are the subproblems overlappin?

3. Are we optimizing, maximizing or minimizing something or counting the total number of possible ways to do something?

If the answer to the first two questions is yes, Dynamic Programming is applicable. Third question is an additional confirmation.

### How to Solve Dynamic Programming Problems

You can solve most of the Dynamic Programming problems by following the below steps:

#### Step 1 - Check

Check if Dynamic Programming is applicable by asking yourself the three questions. 

#### Step 2 - Define Recursion

- Define problem in terms of subproblems. Define it in a top down manner. Do not worry about time complexity at this point.

- Solve the base case. The subproblems are solved by recursion.

- Add a terminating condition. 

After this step, we have a working solution using recursion.

#### Step 3 - Apply Memoization 

If a subproblem is solved multiple times, then cache its solution and use the cached value when same subproblem is encountered again.

#### Step 4 - Solve Bottom Up. 

In this step we eliminate recursion and redefine our solution in forward direction starting from the most basic case. We store only the results that will be required later.
