---
layout: post
title: The Greedy Method
---

The greedy method is the most straightforward design technique. It can be applied to a wide variety of problems. Most of these problems have n inputs and require us to obtain a subset that satisfies some constraints. Any subset that satisfies these constraints is called a feasible solution. 

We are required to find a feasible solution that either maximizes or minimizes a given objective function. A feasible solution that does this is called an optimal solution. There is usually an obvious way to determine a feasible solution, but not necessarily an optimal solution.

<blockquote class="note">
  <strong>THE ESSENCE OF GREEDY METHOD</strong> 
  <p>
    The greedy method suggests that one can devise an algorithm which works in stages, considering one input at a time. At each stage, a decision is made regarding whether or not a particular input is in an optimal solution. This is done by considering the inputs in an order determined by some selection procedure.
  </p>
</blockquote>

If the inclusion of the next input into the partially constructed optimal solution will result in an infeasible solution, then this input is not added to the partial solution. The selection procedure itself is based on some optimization measure. 

This measure may not be the objective function. In fact, several different optimization measures may be plausible for a given problem. Most of these, however, will result in algorithms that generate suboptimal solutions.

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

The function select() selects an input from the input array, removes it and assigns its value to x. The feasible() returns true if x can be included into the solution vector. The union() combines x with solution and updates the objective function. Procedure greedy() describes the essential way that a greedy based algorithm will look, once a particular problem is chosen and the procedures select(), feasible() and union() are properly implemented.

<blockquote class="note">
  <strong>TIP</strong> 
  <p>
    Problems such as knapsack and job sequencing can be solved by using the greedy method program template.
  </p>
</blockquote>
