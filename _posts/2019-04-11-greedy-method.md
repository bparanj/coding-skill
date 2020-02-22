---
layout: post
title: The Greedy Method
---

The Greedy Method is the most straightforward design technique. In each step we choose the most beneficial option in every step without looking into the future. The choice depends only on current profit.

It can be applied to a wide variety of problems. Most of these problems have **n** inputs and require us to obtain a subset that satisfies some constraints. Any subset that satisfies these constraints is called a feasible solution. 

We are required to find a feasible solution that either maximizes or minimizes a given objective function. A feasible solution that does this is called an optimal solution. There is usually an obvious way to determine a feasible solution, but not necessarily an optimal solution.

<blockquote class="note">
  <strong>THE ESSENCE OF GREEDY METHOD</strong> 
  <p>
    The greedy method suggests that one can devise an algorithm which works in stages, considering one input at a time. At each stage, a decision is made regarding whether or not a particular input is in an optimal solution. This is done by considering the inputs in an order determined by some selection procedure.
  </p>
</blockquote>

If the inclusion of the next input into the partially constructed optimal solution will result in an infeasible solution, then this input is not added to the partial solution. The selection procedure itself is based on some optimization measure. 

This measure may not be the objective function. In fact, several different optimization measures may be plausible for a given problem. Most of these, however, will result in algorithms that generate suboptimal solutions.

<blockquote class="note">
  <strong>TIP</strong> 
  <p>
    The Greedy Method is usually a good approach when each profit can be picked up in every step, so no choice blocks another one.
  </p>
</blockquote>

As in the case of dynamic programming algorithms, greedy algorithms are usually designed to solve optimization problems in which a quantity is to be minimized or maximized. 

However, unlike dynamic programming algorithms, greedy algorithms typically consist of an iterative procedure that tries to find a local optimal solution. In some instances, these local optimal solutions translate to global optimal solutions. 

In others, they fail to give optimal solutions. A greedy algorithm makes a correct guess on the basis of little calculation without worrying about the future. Thus, it builds a solution step by step. Each step increases the size of the partial solution and is based on local optimization. 

The choice made is that which produces the largest immediate gain while maintaining feasibility. Since each step consists of little work based on a small amount of information, the resulting algorithms are typically efficient. 

The hard part in the design of a greedy algorithm is proving that the algorithm does indeed solve the problem it is designed for. This is to be contrasted with recursive algorithms that usually have very simple inductive proofs.

Some of the most prominent problems for which the greedy strategy works, i.e., gives an optimal solution: the single-source shortest path problem, minimum cost spanning trees (Prim's and Kruskal's algorithms), and Huffman codes.

<blockquote class="note">
  <strong>BOTTOM LINE</strong> 
  <p>
    Greedy algorithms build up a solution piece by piece, always choosing the next piece that offers the most obvious and immediate benefit. Although such an approach can be disastrous for some computational tasks, there are many for which it is optimal. For example minimum spanning trees.
  </p>
</blockquote>

### Elements of Greedy Algorithms

The two basic properties of optimal Greedy algorithms are:

1. Greedy choice property
2. Optimal substructure

#### Greedy Choice Property

The globally optimal solution can be obtained by making a locally optimal solution (Greedy). The choice may depend on earlier choices but not on the future. It iteratively makes on Greedy choice after another and reduces the given problem to a smaller one.

#### Optimal Substructure

A problem exhibits optimal substructure if an optimal solution to the problem contains optimal solutions to the subproblems. That means we can solve subproblems and build up the solutions to solve larger problems.

### Advantages and Disadvantages

The main advantage of the Greedy method is that it is straightforward, easy to understand and code. Once we make a decision, we do not have to spend timd re-examining the already computed values. Its main disadvantage is that for many problems there is no greedy algorithm. This means, in many cases there is no guarantee that making locally optimal improvements in a locally optimal solution gives the optimal global solution.

### Greedy Method Program Template

We can describe the greedy method abstractly, but more precisely than above by considering the following program template:

```ruby
 # The parameter input array contains the n inputs
def greedy(input, n)
  # Initialize the solution to empty
  solution = {}
  for i in 1..n do
    x = select(input)
    if feasible(solution, x)
      solution = union(solution, x)
    end
  end
end
```

The function _select()_ selects an input from the input array, removes it and assigns its value to x. The _feasible()_ returns true if x can be included into the solution vector. The _union()_ combines x with solution and updates the objective function. The procedure _greedy()_ describes the essential way that a greedy based algorithm will look, once a particular problem is chosen and the procedures _select()_, _feasible()_ and _union()_ are properly implemented.

<blockquote class="note">
  <strong>TIP</strong> 
  <p>
    Problems such as knapsack and job sequencing can be solved by using the greedy method program template.
  </p>
</blockquote>
