---
layout: post
---


A backtracking algorithm tries to construct a solution to a computational problem incrementally, one small piece at a time. Whenever the algorithm needs to decide between multiple alternatives to the next component of the solution, it recursively evaluates every alternative and then chooses the best one.

Backtracking algorithms use recursion to search for the best solution to complicated problems. These algorithms recursively build partial test solutions to solve the problem. When they find that a test solution cannot lead to a usable final solution, they backtrack, discarding that test solution and continuing the search from an earlier test solution.

<blockquote class="note">
  <strong>GENERAL PROBLEM SOLVING</strong> 
  <p>
    A particularly intriguing programming endeavor is the subject of so-called general problem solving. The task is to determine algorithms for finding solutions to specific problems not by following a fixed rule of computation, but by trial and error.
  </p>
</blockquote>

Backtracking is useful when you can incrementally build partial solutions, and you can sometimes quickly determine that a partial solution cannot lead to a complete solution. In that case, you can stop improving that partial solution, backtrack to the previous partial solution, and continue the search from there.

![Backtracking](/assets/images/backtracking.png)

The common pattern is to decompose the trial-and-error process onto partial tasks. Often these tasks are most naturally expressed in recursive terms and consist of the exploration of a finite number of subtasks. 

We may generally view the entire process as a trial or search process that gradually builds up and scans a tree of subtasks. In many problems this search tree grows very rapidly, often exponentially, depending on a given parameter. The search effort increases accordingly. Frequently, the search tree can be pruned by the use of heuristics only, thereby reducing computation to tolerable bounds.

<blockquote class="note">
  <strong>BACKTRACKING</strong> 
  <p>
   In the search for fundamental principles of algorithm design, backtracking represents one of the most general techniques. Many problems which deal with searching for a set of solutions or which as for an optimal solution satisfying some constraints can be solved using the backtracking formulation. 
  </p>
</blockquote>

In many real-world problems, as in most of the NP-hard problems, a solution can be obtained by exhaustively searching through a large but finite number of possibilities. 

Moreover, for virtually all of these problems, there does not exist an algorithm that uses a method other than exhaustive search. Hence, the need arose for developing systematic techniques of searching, with the hope of cutting down the search space to possibly a much smaller space. 

Backtracking is a general technique for organizing the search. This algorithm design technique can be described as an organized exhaustive search which often avoids searching all possibilities. It is generally suitable for solving problems where a potentially large but a finite number of solutions have to be inspected.

In order to apply the backtrack method, the desired solution must be expressible as an n-tuple (x<sub>1</sub> , ...., x<sub>n</sub>) where the x<sub>i</sub> are chosen from some finite set S<sub>i</sub>. Often the problem to be solved calls for finding one vector which maximizes (or minimizes or satisfies) a criterion function P(x<sub>1</sub>, ....., x<sub>n</sub>). 

The general principle consists of breaking up problem-solving tasks into subtasks and applying recursion.

## Iterative Backtracking Program Template

![Iterative Backtracking Method](/assets/images/backtrack-iterative.png)

## Recursive Backtracking Program Template

The following pseudocode shows the general backtracking approach at a high level:

```
  // Explore this test solution.
  // Return false if it cannot be extended to a full solution.
  // Return true if a recursive call to LeadsToSolution finds
  // a full solution.
  Boolean: LeadsToSolution(Solution: test_solution)
      // If we can already tell that this partial solution cannot
      // lead to a full solution, return false.
      If <test_solution cannot solve the problem> Then Return false
      // If this is a full solution, return true.
      If <test_solution is a full solution> Then Return true
      
      // Extend the partial solution.
      
      Loop <over all possible extensions to test_solution>      
      
        <Extend test_solution>
              // Recursively see if this leads to a solution.
              If (LeadsToSolution(test_solution)) Then Return true
              // This extension did not lead to a solution. Undo the change.
              <Undo the extension>
          End Loop
          // If we get here, this partial solution cannot
          // lead to a full solution.
          Return false
      End LeadsToSolution
```

The LeadsToSolution algorithm takes as a parameter whatever data it needs to keep track of a partial solution. It returns true if that partial solution leads to a full solution.

The algorithm begins by testing the partial solution to see if it is illegal. If the test solution so far cannot lead to a feasible solution, the algorithm returns false. The calling instance of LeadsToSolution abandons this test solution and works on others.

If the test solution looks valid so far, the algorithm loops over all the possible ways that it can extend the solution toward a full solution. For each extension, the algorithm calls itself recursively to see whether the extended solution will work. If the recursive call returns false, that extension doesn’t work, so the algorithm undoes the extension and tries again with a new extension.

If the algorithm tries all possible extensions to the test solution and cannot find a feasible solution, it returns false so that the calling instance of LeadsToSolution can abandon this test solution.

You can think of the quest for a solution as a search through a hypothetical decision tree. Each branch in the tree corresponds to a particular decision attempting to solve the problem.

![Recursive Backtracking Method](/assets/images/backtrack-recursive.png)

Reference: Fundamentals of Computer Algorithms by Horowitz and Sahni

## The General Pattern

Backtracking algorithms are commonly used to make a sequence of decisions, with the goal of building a recursively defined structure satisfying certain constraints. Often this goal structure is itself a sequence.

In each recursive call to the backtracking algorithm, we need to make exactly one decision, and our choice must be consistent with all previous decisions.

Thus, each recursive call requires not only the portion of the input data we have not yet processed, but also a suitable summary of the decisions we have already made. For the sake of efficiency, the summary of past decisions should be as small as possible.

When we design new recursive backtracking algorithms, we must figure out in advance what information we will need about past decisions in the middle of the algorithm. If this information is nontrivial, our recursive algorithm might need to solve a more general problem than the one we were originally asked to solve. 

<blockquote class="note">
  <strong>EXAMPLE</strong> 
  <p>
    An example of this kind of generalization: To find the median of an unsorted array in linear time, we derive an algorithm to select the kth smallest element for arbitrary k.
  </p>
</blockquote>

Finally, once we've figured out what recursive problem we really need to solve, we solve that problem by recursive brute force: Try all possibilities for the next decision that are consistent with past decisions, and let the recursion magic do the rest. No being clever here. No skipping "obviously" stupid choices. Try everything. You can make the algorithm faster later.

## Conclusion

Backtracking is a technique where a recursive algorithm considers partial solutions. If it cannot extend a partial solution to a full solution, the algorithm discards the partial solution, backtracks to the previous feasible test solution, and continues searching from there. Examples include the eight queens problem and the knight’s tour problem.
