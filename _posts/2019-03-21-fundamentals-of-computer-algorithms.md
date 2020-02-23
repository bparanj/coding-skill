---
layout: post
title: Fundamentals of Computer Algorithms
excerpt: In this article we will discuss the book Fundamentals of Computer Algorithms by Horowitz and Sahni.
---

In this article we will discuss the book Fundamentals of Computer Algorithms by Horowitz and Sahni. This book covers:

- How to devise and analyze new algorithms?
- How to devise good algorithms?
- Design Techniques

A knowledge of design is needed to create good algorithms. Tools of analysis provides a way to determine the quality of the result.

### Fundamental Strategies of Algorithm Design

The number of basic design strategies is small. All the algorithms you wish to study can easily fit into these categories. For example, mergesort and quicksort are examples of the divide-and-conquer strategy while Kruskal's minimum spanning tree algorithm and Dijkstra's single source shortest path algorithm are straightforward examples of the greedy strategy. 

<blockquote class="note">
  <strong>DESIGN SKILLS</strong> 
  <p>
    An understanding of these strategies is an essential first step towards acquiring the skills of design. However there is no cookbook approach to algorithm design by assuming that each algorithm must derive from only a single technique. 
  </p>
</blockquote>

First each strategy is described in general terms. A program template is given which outlines the form that the computation will take if this strategy can be applied.

The basic design techniques are: 

- [Divide and Conquer]({% post_url 2019-04-04-divide-and-conquer %}) 
- [The Greedy Method]({% post_url 2019-04-11-greedy-method %}) 
- [Dynamic Programming]({% post_url 2019-04-18-dynamic-programming %}) 
- Search and Traversal
- [Backtracking]({% post_url 2019-04-25-backtracking %})   
- Branch and Bound

For each problem we emphasize how the solution can be arrived at by considering a design principle and showing that it applies. Perhaps alternative strategies are investigated and discarded. 

A clean separation is made between how the computation will proceed and decisions about data representation when that is possible. The best case and the worst case data of the resulting algorithm is made clear. Then an analysis of the time and space requirements is done. 

#### Branch and Bound

Branch and bound method is used when we can evaluate cost of visiting each node by a utility functions. At each step, we choose the node with lowest cost to proceed further. Branch and Bound algorithms are implemented using a priority queue. In branch and bound, we traverse the nodes in breadth-first manner.

Branch-and-bound design technique is similar to backtracking in the sense that it generates a search tree and looks for one or more solutions. However, while backtracking searches for a solution or a set of solutions that sat- isfy certain properties (including maximization or minimization), branch-and-bound algorithms are typically concerned with only maximization or minimization of a given function. 

Moreover, in branch-and-bound algorithms, a bound is calculated at each node x on the possible value of any solution given by nodes that may later be generated in the subtree rooted at x. If the bound calculated is worse than a previous bound, the subtree rooted at x is blocked, i.e., none of its children are generated.

<blockquote class="note">
  <strong>BRANCH AND BOUND</strong> 
  <p>
    As a branch-and-bound algorithm searches a tree, it keeps track of the best solution it has found so far and the best possible solution that it can find from the current point in the tree. If the best possible solution from that point cannot beat the current best solution, the algorithm abandons that node and considers other paths through the tree. Branch and bound can be much faster than exhaustive search for finding an optimal solution, but it doesn't change the algorithm's Big O run time.
  </p>
</blockquote>

### How to Devise Algorithms

The act of creating an algorithm is an art which may never be fully automated. This book provides various design techniques which have proven to be useful in that they have often yielded good algorithms. By mastering these design strategies, it will become easier for you to devise new and useful algorithms. 

This book is organized around the major methods of algorithm design. It gives an introduction to many approaches to algorithm formulation. 

### How to Express Algorithms

The structured programming is about the clear and concise expression of algorithms in a programming language. Good books on these topics are: 

- Structured Programming by Dahl, Dijkstra and Hoare (Academic Press)  
- The Elements of Programming Style by Kernighan and Plauger (McGraw Hill)

The process of reading a well composed program will improve your own skills.

### How to Analyze Algorithms

This field of study is called analysis of algorithms. An as algorithm is executed, it makes use of the computer's CPU to perform operations and it uses the memory (both immediate and auxiliary) to hold the program and its data. 

Analysis of Algorithms refers to the process of determining how much computing time and storage an algorithm will require. We can predict if our software will meet any efficiency constraints. We can compare the value of one algorithm over another. 
