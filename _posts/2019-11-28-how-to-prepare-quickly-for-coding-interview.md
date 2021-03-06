---
layout: post
title: How to Prepare Quickly for Coding Interviews
excerpt: Learn the ultimate strategy to prepare for a coding interview. We will see how we can solve several problems per day instead of spending the entire day on a handful of problems.
---

## Categorize Problems

You can categorize problems into problem types by observing common traits of problems with similar solutions. Problem from a problem type can be solved using the same technique. For instance:

### Breadth First Search

The problems that use BFS usually ask to find the fewest number of steps or the shortest path needed to reach a state. We might have tables that represent mazes, maps, cities and other similar things.

Similarly you can identify problem types such as:

- [Backtracking]({% post_url 2019-04-25-backtracking %})
- [Dynamic Programming]({% post_url 2019-04-18-dynamic-programming %})
- [Linear Programming](/2019/11/28/how-to-prepare-quickly-for-coding-interview.html#linear-programming)

And so on. 

#### Linear Programming

Instead of looking for a candidate for a [reduction]({% post_url 2018-11-29-reductions %}) whenever a new problem arises, we explore some "super-problems", to which many problems can be reduced. One such super-problem, perhaps the most important one is linear programming.

Many of the problems for which we want algorithms are optimization tasks: 

- The shortest path 
- The cheapest spanning tree 
- The longest increasing subsequence

and so on. In such cases, we seek a solution that: 

1. Satisfies certain constraints (for instance, the path must use edges of the graph and lead from s to t, the tree must touch all nodes, the subsequence must be increasing); and 

2. Is the best possible, with respect to some well-defined criterion, among all solutions that satisfy these constraints.

Linear programming describes a broad class of optimization tasks in which both the constraints and the optimization criterion are linear functions. It turns out an enormous number of problems can be expressed in this way.

## Map Problem Types to Solution Types

Read the problem description and write down the problem hints. The hints are useful to detect the problem type. Identify the hints in the problem statement and determine the type of the solution.

Solution for a similar problem can be discovered by adjusting the solution to a known problem within the same problem type. Focus on practicing problem types instead of focusing on quantity of problems solved. It is practical to practice hundred types of problems rather than a thousand problems. Recognize variations of a given problem type.

You can read about [Mapping Problem Types to Algorithm Strategies](/2020/01/23/problem-solving-techniques-for-coding-interview.html#mapping-problem-types-to-algorithm-strategies)

## Map Data Structures to Problems

One of the challenges to solving a coding problem is picking the right data structure. Given a problem, you need to first recognize what data structure to use to solve that problem. [Schedule a call](https://go.oncehub.com/BalaParanj) with me to get access to a list of problems that is mapped to data structures.

## Map Problem Solving Strategy to Problems

[Dynamic Programming]({% post_url 2019-04-18-dynamic-programming %}) can be divided into top-down and bottom-up design. If you can quickly identify which problems require a Dynamic Programming algorithm, you can use one of these two strategies to quickly tackle the problem.

## Structure of the Solution

If you squint your eyes and look at the source code, you will see the shape of the code caused by indentation. This is the structure of the solution. Remember the problem type and the structure to solve that problem type. The structure does not depend on a specific programming language. For instance: does the solution really require nested loops? 

Some of the structure in the solution can be mapped to time complexity. Create a table that maps structure and time complexity. As you study and observe the relationship between structure and time complexity, this table will grow over time.

<blockquote class="note">
  <strong>STRUCTURE</strong> 
  <p>
    One way to learn about the structure is to look at the pseudocode of the solution.
  </p>
</blockquote>
