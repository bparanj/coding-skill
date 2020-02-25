---
layout: post
title: Branch and Bound
---

Many problems involve minimizing or maximizing a target value: find the shortest path, get the maximum profit, etc. They’re called optimization problems. When the solution is a sequence of choices, we often use a strategy called branch and bound. 

Its aim is to gain time by quickly detecting and discarding bad choices. To understand how bad choices are detected, we first need to learn the concepts of upper and lower bounds.

### Upper and Lower Bounds

Bounds refer to the range of a value. An upper bound sets a limit on how high the value can be. A lower bound is the least one can hope for: it guarantees the value is equal to it or greater.

We can often easily get suboptimal solutions: a short path, but maybe not the shortest; a big profit, but maybe not the biggest. These solutions provide bounds to the optimal solution. 

For instance, the shortest route between two places is never shorter than their straight linear distance. The linear distance is thus a lower bound of the shortest driving distance.

### How does it Work?

1. Divide the problem into subproblems.
2. Find upper and lower bounds of each new subproblem.
3. Compare subproblem bounds of all branches.
4. Return to step 1 with the most promising subproblem.

The backtracking strategy also led to the solution without exploring every possible solution candidate. In backtracking, we remove paths after having explored them as far as we can, and we stop when we’re OK with a solution. With branch and bound, we predict which paths are worst and we avoid wasting energy exploring them.

### Implementation

Branch and bound method is used when we can evaluate cost of visiting each node by a utility functions. At each step, we choose the node with lowest cost to proceed further.

Branch and Bound algorithms are implemented using a priority queue. In branch and bound, we traverse the nodes in breadth-first manner.

### Backtracking vs Branch and Bound

Branch-and-bound design technique is similar to backtracking in the sense that it generates a search tree and looks for one or more solutions. However, while backtracking searches for a solution or a set of solutions that satisfy certain properties (including maximization or minimization), branch-and-bound algorithms are typically concerned with only maximization or minimization of a given function. 

Moreover, in branch-and-bound algorithms, a bound is calculated at each node x on the possible value of any solution given by nodes that may later be generated in the subtree rooted at x. If the bound calculated is worse than a previous bound, the subtree rooted at x is blocked, i.e., none of its children are generated.

### Searching a Tree

As a branch-and-bound algorithm searches a tree, it keeps track of the best solution it has found so far and the best possible solution that it can find from the current point in the tree. 

If the best possible solution from that point cannot beat the current best solution, the algorithm abandons that node and considers other paths through the tree. 

Branch and bound can be much faster than exhaustive search for finding an optimal solution, but it doesn't change the algorithm's Big O run time.

### A* Algorithm

A* is sort of an elaboration on branch-and-bound. In branch-and-bound, at each iteration we expand the shortest path that we have found so far. 

In A*, instead of just picking the path with the shortest length so far, we pick the path with the shortest estimated total length from start to goal, where the total length is estimated as length traversed so far plus a heuristic estimate of the remaining distance from the goal.

Branch-and-bound will always find an optimal solution that is shortest path. A* will always find an optimal solution if the heuristic is correct. Choosing a good heuristic is the most important part of A* algorithm.
