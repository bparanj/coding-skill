---
layout: post
---

A backtracking algorithm tries to construct a solution to a computational problem incrementally, one small piece at a time. Whenever the algorithm needs to decide between multiple alternatives to the next component of the solution, it recursively evaluates every alternative and then chooses the best one.

Imagine someone gave you a lock with a number (three digit lock, number range from 1 to 9). Moreover, you do not have the exact password key for the lock. You need to test every combination until you got the right one. 

Obviously, you need to test starting from something like “111”, then “112” and so on. You will get your key before you reach “999”. This is backtracking.

Let's say the lock produces a clicking sound when correct digit is selected for any level. If we can listen to this sound such intelligence / heuristics will help you to reach your goal much faster. 

These functions are called Pruning function or bounding functions. Backtracking is a method by which solution is found by exhaustively searching through large but finite number of states, with some pruning or bounding function that will narrow down our search. 

<blockquote class="note">
  <strong>WHEN TO APPLY</strong> 
  <p>
    Problems (NP hard problems) that lack any other method we use backtracking.
  </p>
</blockquote>

Backtracking problems have the following components:

1. Initial state
2. Target / Goal state
3. Intermediate states
4. Path from the initial state to the target / goal state
5. Operators to get from one state to another
6. Pruning function (optional)

The solving process of backtracking algorithm starts with the construction of state’s tree, whose nodes represents the states. The root node is the initial state and one or more leaf node will be our target state. Each edge of the tree represents some operation. The solution is obtained by searching the tree until a Target state is found.

Backtracking uses depth-first search:

1. Store the initial state in a stack
2. While the stack is not empty, repeat:
3. Read a node from the stack.
4. While there are available operators, do:
    a. Apply an operator to generate a child
    b. If the child is a goal state – return solution
    c. If it is a new state, and pruning function does not discard it push the child into the stack.

### Recursion

Backtracking algorithms use recursion to search for the best solution to complicated problems. These algorithms recursively build partial test solutions to solve the problem. When they find that a test solution cannot lead to a usable final solution, they backtrack, discarding that test solution and continuing the search from an earlier test solution.

<blockquote class="note">
  <strong>GENERAL PROBLEM SOLVING</strong> 
  <p>
    A particularly intriguing programming endeavor is the subject of so-called general problem solving. The task is to determine algorithms for finding solutions to specific problems not by following a fixed rule of computation, but by trial and error.
  </p>
</blockquote>

### Partial Solutions

Backtracking is useful when you can incrementally build partial solutions, and you can sometimes quickly determine that a partial solution cannot lead to a complete solution. In that case, you can stop improving that partial solution, backtrack to the previous partial solution, and continue the search from there.

![Backtracking](/assets/images/backtracking.png)

### Partial Tasks

The common pattern is to decompose the trial-and-error process onto partial tasks. Often these tasks are most naturally expressed in recursive terms and consist of the exploration of a finite number of subtasks. 

### Pruning

We may generally view the entire process as a trial or search process that gradually builds up and scans a tree of subtasks. In many problems this search tree grows very rapidly, often exponentially, depending on a given parameter. The search effort increases accordingly. Frequently, the search tree can be pruned by the use of heuristics only, thereby reducing computation to tolerable bounds.

<blockquote class="note">
  <strong>BACKTRACKING</strong> 
  <p>
   In the search for fundamental principles of algorithm design, backtracking represents one of the most general techniques. Many problems which deal with searching for a set of solutions or which as for an optimal solution satisfying some constraints can be solved using the backtracking formulation. 
  </p>
</blockquote>

### Exhaustive Search

In many real-world problems, as in most of the NP-hard problems, a solution can be obtained by exhaustively searching through a large but finite number of possibilities. 

Moreover, for virtually all of these problems, there does not exist an algorithm that uses a method other than exhaustive search. Hence, the need arose for developing systematic techniques of searching, with the hope of cutting down the search space to possibly a much smaller space. 

Backtracking is a general technique for organizing the search. This algorithm design technique can be described as an organized exhaustive search which often avoids searching all possibilities. It is generally suitable for solving problems where a potentially large but a finite number of solutions have to be inspected.

### Brute Force and Backtracking

Backtracking is an improvement of the brute force approach. It systematically searches for a solution to a problem among all available options. 

We start with on possible option out of many available options and try to solve the problem if we are able to solve the problem with the selected move. Then we will print the solution otherwise we will backtrack and select some other option and try to solve it. If none of the options work out, we will claim that there is no solution for the problem.

### Applying Backtrack Method

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

Backtracking allows us to deal with situations in which a raw brute-force approach would explode into an impossible number of options to consider. 

At each node, we eliminate choices that are obviously not possible and proceed to recursively check only those that have potential. We back up only as far as needed to reach a previous decision point with an as-yet-unexplored alternative. 

In general, that will be at the most recent decision point. Eventually, more and more of these decision points will have been fully explored and we will have to backtrack further and further. 

If we backtrack all the way to our initial state and have explored all alternatives from there, we can conclude the particular problem is unsolvable. In such a case, we have done all the work of the exhaustive recursion and know that there is no viable solution possible.

<blockquote class="note">
  <strong>TIP</strong> 
  <p>
    Backtracking speeds the exhaustive search by pruning.
  </p>
</blockquote>

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

**References**

- Fundamentals of Computer Algorithms by Horowitz and Sahni
- Essential Algorithms A Practical Approach to Computer Algorithms using Python and C by Rod Stephens

## Why is backtracking called a modified depth-first search of a tree?

The backtracking algorithm traverses the search tree recursively, from the root down, in depth-first order. At each node c, the algorithm checks whether c can be completed to a valid solution. If it cannot, the whole sub-tree rooted at c is skipped (pruned). Otherwise, the algorithm:

1. Checks whether c itself is a valid solution, and if so reports it to the user; and 
2. Recursively enumerates all sub-trees of c. The two tests and the children of each node are defined by user-given procedures.

The backtracking algorithm enumerates a set of partial candidates that, in principle, could be completed in various ways to give all the possible solutions to the given problem. The completion is done incrementally, by a sequence of candidate extension steps.

Conceptually, the partial candidates are represented as the nodes of a tree structure, the potential search tree. Each partial candidate is the parent of the candidates that differ from it by a single extension step; the leaves of the tree are the partial candidates that cannot be extended any further.

Therefore, the actual search tree that is traversed by the algorithm is only a part of the potential tree. The total cost of the algorithm is the number of nodes of the actual tree times the cost of obtaining and processing each node. This fact should be considered when choosing the potential search tree and implementing the pruning test.

### Pseudocode

In order to apply backtracking to a specific class of problems, one must provide the data P for the particular instance of the problem that is to be solved, and six procedural parameters, root, reject, accept, first, next, and output. These procedures should take the instance data P as a parameter and should do the following:

1. root(P): return the partial candidate at the root of the search tree.
2. reject(P,c): return true only if the partial candidate c is not worth completing.
3. accept(P,c): return true if c is a solution of P, and false otherwise.
4. first(P,c): generate the first extension of candidate c.
5. next(P,s): generate the next alternative extension of a candidate, after the extension s.
6. output(P,c): use the solution c of P, as appropriate to the application.

The backtracking algorithm reduces the problem to the call **bt(root(P))**, where **bt** is the following recursive procedure:

```python
procedure bt(c)
  if reject(P,c) then return
  if accept(P,c) then output(P,c)
  s ← first(P,c)
  while s ≠ Λ do
    bt(s)
    s ← next(P,s)
```

## When to use backtracking to solve problems?

- You should use backtracking while solving crosswords, Sudoku and many other kind of puzzles.
- Backtracking method is mainly used for solving the constraint satisfactions problem where specific constrains are needed to be satisfied.
- It is also used for solving the problems related to the State space have size of factorial .Example of such problem is Travelling sales man Problem
