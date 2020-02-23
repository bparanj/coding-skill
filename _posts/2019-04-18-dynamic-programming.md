---
layout: post
title: Dynamic Programming
excerpt: Dynamic Programming is an algorithm design method that can be used when the solution to a problem may be viewed as the result of a sequence of decisions. Some examples are Knapsack, Optimal Merge Patterns and Shortest Path.
---

Dynamic Programming is a powerful algorithm design technique that is widely used to solve [combinatorial optimization problems](/2019/10/24/how-to-set-goal-and-create-an-action-plan.html#combinatorial-problems). An algorithm that employs this technique is not recursive by itself, but the underlying solution of the problem is usually stated in the form of a recursive function. 

Examples:

- Fibonacci numbers computed by iteration
- Warshall’s algorithm for transitive closure implemented by iterations
- Floyd’s algorithms for all-pairs shortest paths

### Bottom-Up Evaluation

Unlike the case in divide-and-conquer algorithms, immediate implementation of the recurrence results in identical recursive calls that are executed more than once. For this reason, this technique resorts to evaluating the recurrence in a bottom-up manner, saving intermediate results that are used later on to compute the desired solution. 

### Combinatorial Optimization Problems

Dynamic programming is a general-purpose algorithm design technique that is most often used to solve combinatorial optimization problems, where we are looking for the best possible input to some function chosen from an exponentially large search space.

It is also used to improve the time complexity of the brute-force methods to solve some of the NP-hard problems.

<blockquote class="note">
  <strong>BOTTOM LINE</strong> 
  <p>
    This technique applies to many combinatorial optimization problems to derive efficient algorithms.
  </p>
</blockquote>

### Parts of Dynamic Programming

There are two parts to dynamic programming. The first part is a programming technique: dynamic programming is essentially [Divide and Conquer]({% post_url 2019-04-04-divide-and-conquer %}) run in reverse: we solve a big instance of a problem by breaking it up recursively into smaller instances; but instead of carrying out the computation recursively from the top down, we start from the bottom with the smallest instances of the problem, solving each increasingly large instance in turn and storing the result in a table. 

The second part is a design principle: in building up our table, we are careful always to preserve alternative solutions we may need later, by delaying commitment to particular choices to the extent that we can.

The bottom-up aspect of dynamic programming is most useful when a straightforward recursion would produce many duplicate subproblems. It is most efficient when we can enumerate a class of subproblems that doesn’t include too many extraneous cases that we don’t need for our original problem.

<blockquote class="note">
  <strong>TIP</strong> 
  <p>
    Dynamic Programming is an algorithm design method that can be used when the solution to a problem may be viewed as the result of a sequence of decisions.
  </p>
</blockquote>
 
For some of the problems that may be viewed in this way, an optimal sequence of decisions may be found by making the decisions one at a time and never making an erroneous decision. 

This is true for all problems solvable by the [greedy method]({% post_url 2019-04-11-greedy-method %}). For many other problems, it is not possible to make stepwise decisions (based only on local information) in such a manner that the sequence of decisions made is optimal. 

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

Thus, the essential difference between the [greedy method]({% post_url 2019-04-11-greedy-method %}) and dynamic programming is that in the greedy method only one decision sequence is ever generated. In dynamic programming, many decision sequences may be generated. However, sequences containing suboptimal subsequences cannot be optimal (if the principle of optimality holds) and so will not be generated.

An important feature of the dynamic programming approach is that optimal solutions to subproblems are retained so as to avoid recomputing their values. The use of these tabulated values makes it natural to recast the recursive equations into an iterative program. 

<blockquote class="note">
  <strong>KEY TAKE AWAYS</strong> 
  <p>
    Dynamic Programming is a widely used concept. It is often used for optimization. It refers to simplifying a complicated problem by breaking it down into simpler sub-problems in a recursive manner usually by applying the Bottom Up Approach. 
  </p>
</blockquote>

### Problem Requirements

There are two key attributes that a problem must have in order for dynamic programming to be applicable: 

- Overlapping Subproblems
- Optimal Substructure

Overlapping Subproblems means that results of smaller versions of the problem are reused multiple times in order to arrive at the solution to the original problem.

Optimal Substructure means that an optimal solution to a problem contains optimal solutions to sub problems.

<blockquote class="note">
  <strong>OPTIMIZATION</strong> 
  <p>
    Dynamic Programming uses a concept called Memoization to achieve its optimization.
  </p>
</blockquote>

Dynamic programming uses memoization to maintain a table of sub problems that already been solved. So it reduces the exponential complexity to polynomial complexity (O(n<sup>2</sup>), O(n<sup>3</sup>), etc.) for many problems. Memoization means caching. 

<blockquote class="note">
  <strong>QUICK TIP</strong> 
  <p>
    Dynamic Programming = Recursion + Memoization
  </p>
</blockquote>

If the subproblems are independent and there is no repetition in calculation then memoization has no effect, so recursion can be used instead of dynamic programming.

### Solution Components

A Dynamic Programming Solution has 2 main components, the State and the Transition

- The State refers to a subproblem of the original problem.
- The Transition is the method to solve a problem based on its subproblems.

The time taken by a Dynamic Programming Solution can be calculated as:

```
No. of States * Transition Time 
```

Thus if a solution has N<sup>2</sup> states and the transition is O(N), then the solution would take roughly O(N<sup>3</sup>) time.

### Is Dynamic Programming Applicable?

Ask yourself the following questions:

1. Is it possible to divide the problem into subproblems of the same type?

2. Are the subproblems overlapping?

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

### Dynamic Programming Approaches

There are two approaches for solving Dynamic Programming problems:

- Bottom Up Dynamic Programming
- Top Down Dynamic Programming

#### Bottom Up Dynamic Programming

In this method, we evaluate the function starting with the smallest possible input argument value and then we step through possible values, slowly increasing the input argument value. We store the computed values in a hashtable. As larger arguments are evaluated, pre-computed values for smaller arguments can be used.

#### Top Down Dynamic Programming

In this method, the problem is broken into sub problems. Each of these sub problems is solved. The solutions are remembered, in case they need to be solved. Also, we save each computed value as the final action of the recursive function. As the first action, we check if pre-computed value exists.

## Conclusion

The [Divide and Conquer]({% post_url 2019-04-04-divide-and-conquer %}), graph exploration, and greedy choice yield definitive algorithms for a variety of important computational tasks. The drawback of these tools is that they can only be used on very specific types of problems. 

Dynamic programming and [linear programming](/2019/11/28/how-to-prepare-quickly-for-coding-interview.html#linear-programming) techniques have a very broad applicability that can be invoked when more specialized methods fail. Predictably, this generality often comes with a cost in efficiency.
