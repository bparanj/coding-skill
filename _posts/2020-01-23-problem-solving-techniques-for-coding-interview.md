---
layout: post
title: Problem Solving Techniques for Coding Interview
excerpt: In a coding interview you have to demonstrate to your interviewer that you possess several key skills. The ability to rigorously formulate real-world problems. The skills to solve problems and design algorithms. The tools to go from an algorithm to a working program.  The analytical techniques required to determine the computational complexity of your solution.
---

In a coding interview you have to demonstrate to your interviewer that you possess several key skills:

- The ability to rigorously formulate real-world problems.
- The skills to solve problems and design algorithms.
- The tools to go from an algorithm to a working program.
- The analytical techniques required to determhe the computational complexity of your solution.

You must demonstrate that you are familiar with approaches that you can use to solve problems.

There are a number of approaches to designing algorithms: 

- Exhaustive Search 
- [Divide and Conquer]({% post_url 2019-04-04-divide-and-conquer %})
- [Greedy Method]({% post_url 2019-04-11-greedy-method %})
- [Randomized](#randomization)
- Parallelization
- [Backtracking]({% post_url 2019-04-25-backtracking %})
- Heuristics
- [Reduction](#reduction)
- Approximation
 
And so on.

### Exhaustive Search 

Exhaustive Search is simply a [Brute Force](#brute-force) approach to combinatorial problems. It suggests generating each and every element of the problem domain, selecting those of them that satisfy all the constraints, and then finding a desired element.

In certain cases, as we explore the various alternatives in a brute force algorithm, we discover that we can omit a large number of alternatives, a technique that is often called [Branch and Bound](/2019/03/21/fundamentals-of-computer-algorithms.html#branch-and-bound).

### Heuristics

Many trees are enormous for large problem sizes, so often they cannot be solved exactly, and you must turn to heuristics. Heuristics that can apply to any decision tree include random search, improving paths, and simulated annealing. Hill climbing and sorted hill climbing often can give good results extremely quickly, although you need to define what hill climbing means for a particular problem.

### Applying Problem Solving Techniques

The book Algorithms for Interviews by Aziz and Prakash covers some common problem solving techniques. It works through several coding problems to illustrate how to apply these problem solving techniques to a coding problem. 

You still need to learn which technique to apply to a given problem. Let's briefly look at these problem solving techniques. 

### Divide and Conquer

- Can you break the problem into pieces that are easier to solve?
- Can you divide the problem into two or more smaller independent subproblems and solve the original problem using solutions to the subproblems?

### Recursion and Dynamic Programmmg

If you have access to solutions for smaller instances of a given problem, can you easily construct a solution to the problem?

### Case Analysis

Can you split the input/execution into a number of cases and solve each case in isolation?

### Generalization

Is there a problem that subsumes your probem and is easier to solve?

### Data Structures

- Is there a data structure that directly maps to the given problem?

- Does a certain data structure such as linked list, array, stack, queue, tree, balanced tree, network map naturally to the problem? 

- Does a certain data structure have behaviors similar to the ones that you need to solve the problem?

### Iterative Refinement

Most problems can be solved using a brute-force approach. Can you formalize such a solution and improve it?

### Small Examples

Can you find a solution to small concrete instances of the problem and then build a solution that can be generalized to arbitrary instances?

### Reduction

Reduction is the single most common technique used in designing algorithms. Reducing one problem X to another problem Y means to write an algorithm for X that uses an algorithm for Y as a black box. 

A problem A reduces to a problem B, if an algorithm that solves B can be easily translated into one that solves A. For example, the problem of computing the median element of an array reduces to the problem of sorting the array. 

You should always be on the lookout for reductions. Whenever you encounter a seemingly new problem, always ask: 

- Is the problem a disguised version of one you already know how to solve? 
- Can you reduce the general version of the problem to a special case?
- Can you use a problem with a known solution as a subroutine?

<blockquote class="note">
  <strong>TIP</strong> 
  <p>
    You should always be on the lookout for reductions to problems you already know how to solve.
  </p>
</blockquote>

### Graph Modeling

Can you describe your problem using a graph and solve it using an existing algorithm?

### Write an Equation

Can you express relationships in your problem in the form of equations (or inequalities)?

### Auxiliary Elements

Can you add some new element to your problem to get closer to a solution?

### Variation

Can you solve a slightly different problem and map its solution to your problem?

### Parallelism

Can you decompose your problem into sub-problems that can be solved independently on different machines?

### Caching

Can you store some of your computation and look it up later to save work?

### Symmetry

Is there symmetry in the input space or solution space that can be exploited?

### Randomization

Does the problem include worst cases that could be avoided with randomization?

### Probability

Can you think of a probabilistic method that uses guesses to find a solution or that solves the problem with a given probability?

<blockquote class="note">
  <strong>PROBABILISTIC ALGORITHM</strong> 
  <p>
    An algorithm that produces a result with a given certainty is probabilistic. For example, the Fermat primality test detects nonprime numbers at least 50 percent of the time. If you repeat the test many times, you can conclude that a number is prime with great certainty.
  </p>
</blockquote>

### Adaptive Techniques

Many algorithms can be improved if you focus more work on the parts of the problem that are the most difficult and you spend less work on parts of the problem that are easy to handle.

- Can you think of an approach that focuses on specific parts of the problem? 
- Are there really only a few true areas of interest, with the rest of the problem being there to confuse the issue?

### Problem Structure

- Is the problem’s structure naturally recursive, hierarchical, or similar to a network? 
- Can you use tree or network algorithms to search the data?

### Decision Trees

Can you apply decision tree search methods to the problem? Often you can, but it would take too long. You might say, "Well, we could try examining all possible combinations of the data, but that would take forever. Perhaps a divide-and-conquer approach would be better."

<blockquote class="note">
  <strong>RULES</strong> 
  <p>
    Expert programmers do not rely on a set of rules. But the journey to becoming an expert programmer cannot bypass the phase where you need a set of rules to learn problem solving in the context of solving coding problems.
  </p>
</blockquote>

## Algorithm Design

Algorithm design often requires both creativity and problem-specific knowledge, but there are certain common techniques that appear over and over again. 

The following classification is adapted from Anany Levitin, Introduction to the Design & Analysis of Algorithms, Addison-Wesley, 2003.

### Brute Force

Brute force is a straightforward approach to solving a problem, usually directly based on the problem statement and definitions of the concepts involved. In this approach we try all possible solutions until we find the right one.

It is one of the easiest approaches to solve a particular problem. It is useful for solving small size dataset
problem. Some examples of brute force algorithms are:

- Bubble-Sort
- Selection-Sort
- Sequential search in an array
- Computing power(a, n) by multiplying a, n times.
- Convex hull problem
- String matching
- Exhaustive search: Traveling salesman, Knapsack, and Assignment problems

In general, brute force algorithms are too slow to be practical for anything but the smallest instances and you should always think how to avoid the brute force algorithms or how to finesse them into faster versions.

### Divide and Conquer

Split the problem into two or more subproblems, solve the subproblems recursively, and then combine the solutions. Examples of divide-and-conquer algorithms using recursion:

- Merge-Sort algorithm 
- Quicksort algorithm 
- Computing the length of the longest path in a binary tree 
- Computing Fibonacci numbers

Quick-hull is an example of Divide and Conquer without recursion.

### Decrease and Conquer

In Divide and Conquer the size of the problem is reduced by a factor (half, one-third, etc.), While in Decrease and Conquer the size of the problem is reduced by a constant.

We reduce the problem to a single smaller problem, solve that problem recursively, and then use that solution to solve the original problem.

Decrease and Conquer is a simpler strategy than Divide and Conquer. Decrease and Conquer is applicable to more problems than Divide and Conquer. Examples of decrease-and-conquer algorithms:

- Computing power(a, n) by calculating power(a, n/2) using recursion.
- Binary search in a sorted array (using recursion)
- Searching in BST
- Insertion Sort
- Topological sort
- Graph traversal algorithms (DFS and BFS)
- Warshall's algorithm (using recursion)
- Permutations (Minimal change approach, Johnson-Trotter algorithm)
- Computing a median
- Fake-coin problem (Ternary search)

### Transform and Conquer

In this method we solve a difficult problem by transforming it into a known problem for which we have asymptotically optimal algorithms. In this method, the goal is to find a reducing algorithm whose complexity is not dominated by the resulting reduced algorithms. 

For example, the selection algorithm for finding the median in a list involves first sorting the list and then finding out the middle element in the sorted list. This technique is also called as reduction.

We either: 

- Transform the input to a form that makes the problem easy to solve or 
- Transform the input into the input to another problem whose solution solves the original problem.

This works as two-stage procedure. First, the problem is transformed into a known problem for which we know optimal solution. In the second stage, the problem is solved. The most common type of transformation is sorting of an array.

For example, given an array of numbers find the two closest number. The brute force solution for this problem will take distance between each element in the array and
will try to keep the minimum distance pair. This approach has a Time Complexity of O(n<sup>2</sup>).

In Transform and Conquer solution, we first sort the array in O(n log n) time and then find the closest number by scanning the array in another O(n). This has the total Time Complexity of O(n log n).

Examples:

- Gaussian elimination
- Heaps and Heapsort

### Use Space

Solve the problem using some auxiliary data structure.

### Dynamic Programming

Construct a table of solutions for increasingly large subproblems, where each new entry in the table is computed using previous entries in the table. Read more on [Dynamic Programming]({% post_url 2019-04-18-dynamic-programming %})

### Greedy method

Run through your problem one step at a time, keeping track of the single best solution at each step.

<blockquote class="note">
  <strong>TIP</strong> 
  <p>
    Some of these approaches work better than others. It is the role of algorithm analysis to figure out which are likely to be both correct and efficient in practice. But having all of them in your toolbox lets you try different possibilities for a given problem.
  </p>
</blockquote>

## Conclusion

The high level strategic decisions are data structures, algorithms and problem solving strategies and the tactical decisions at the code level are coding patterns, coding drills and the semantics. You need a good grasp of both aspects to become a problem solver capable of solving new problems.

You already need to know the basic data structures and algorithms to read this book. The authors recommend the book Algorithms by Dasgupta, Papadirnitriou, and Vazirani because it is succinct and beautifully written.

In upcoming articles, we will see the forest as well as the trees by discussing both the big picture as well as the lower level details that fit into the higher level structure. 
