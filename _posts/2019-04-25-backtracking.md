---
layout: post
---

A backtracking algorithm tries to construct a solution to a computational problem incrementally, one small piece at a time. Whenever the algorithm needs to decide between multiple alternatives to the next component of the solution, it recursively evaluates every alternative and then chooses the best one.

A particularly intriguing programming endeavor is the subject of so-called general problem solving. The task is to determine algorithms for finding solutions to specific problems not by following a fixed rule of computation, but by trial and error. 

![Backtracking](/assets/images/backtracking.png)

The common pattern is to decompose the trial-and-error process onto partial tasks. Often these tasks are most naturally expressed in recursive terms and consist of the exploration of a finite number of subtasks. 

We may generally view the entire process as a trial or search process that gradually builds up and scans a tree of subtasks. In many problems this search tree grows very rapidly, often exponentially, depending on a given parameter. The search effort increases accordingly. Frequently, the search tree can be pruned by the use of heuristics only, thereby reducing computation to tolerable bounds.

<blockquote class="note">
  <strong>BACKTRACKING</strong> 
  <p>
   In the search for fundamental principles of algorithm design, backtracking represents one of the most general techniques. Many problems which deal with searching for a set of solutions or which as for an optimal solution satisfying some constraints can be solved using the backtracking formulation. 
  </p>
</blockquote>

In order to apply the backtrack method, the desired solution must be expressible as an n-tuple (x<sub>1</sub> , ...., x<sub>n</sub>) where the x<sub>i</sub> are chosen from some finite set S<sub>i</sub>. Often the problem to be solved calls for finding one vector which maximizes (or minimizes or satisfies) a criterion function P(x<sub>1</sub>, ....., x<sub>n</sub>). 

The general principle consists of breaking up problem-solving tasks into subtasks and applying recursion.

## Iterative Backtracking Program Template

![Iterative Backtracking Method](/assets/images/backtrack-iterative.png)

## Recursive Backtracking Program Template
![Recursive Backtracking Method](/assets/images/backtrack-recursive.png)

Reference: Fundamentals of Computer Algorithms by Horowitz and Sahni

## The General Pattern

Backtracking algorithms are commonly used to make a sequence of decisions, with the goal of building a recursively defined structure satisfying certain constraints. Often this goal structure is itself a sequence.

In each recursive call to the backtracking algorithm, we need to make exactly one decision, and our choice must be consistent with all previous decisions.

Thus, each recursive call requires not only the portion of the input data we have not yet processed, but also a suitable summary of the decisions we have already made. For the sake of efficiency, the summary of past decisions should be as small as possible.

When we design new recursive backtracking algorithms, we must figure out in advance what information we will need about past decisions in the middle of the algorithm. If this information is nontrivial, our recursive algorithm might need to solve a more general problem than the one we were originally asked to solve. 

An example of this kind of generalization: To find the median of an unsorted array in linear time, we derive an algorithm to select the kth smallest element for arbitrary k.

Finally, once we've figured out what recursive problem we really need to solve, we solve that problem by recursive brute force: Try all possibilities for the next decision that are consistent with past decisions, and let the recursion magic do the rest. No being clever here. No skipping "obviously" stupid choices. Try everything. You can make the algorithm faster later.
