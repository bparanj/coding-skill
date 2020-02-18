---
layout: post
title: Divide and Conquer Strategy
---

Given a function to compute on n inputs, the divide and conquer strategy splits the input into k distinct subsets, yielding k subproblems. These subproblems must be solved and then a method must be found to combine subsolutions into a solution of the whole. 

If the subproblems are large, then the divide and conquer strategy may possibly be reapplied. Often the subproblems resulting from a divide and conquer design are of the same type as the original problem. For those cases, the reapplication of the divide and conquer principle is naturally expressed by a recursive procedure. 

Now smaller and smaller subproblems of the same kind as the original problem are generated, eventually producing subproblems that are small enough to be solved without splitting.

We can write a program template which mirrors the way an actual program based upon divide-and-conquer will look. By a program template we mean a procedure whose flow of control is clear, but whose primary operations are specified by other procedures whose precise meaning is left undefined. 

### Recursive Program Template

Let the n inputs be stored by the array called input. Here is the program template for divide and conquer:

```ruby
def solve(p, q)
   input 
  # 1 <= p <= q <= n 
  if small(p, q)
    return compute(p, q)
  else
    m = divide(p, q)
    # p <= m < q 
    solution = combine(solve(p, m), solve(m + 1, q))        
  end
end
```

small(p, q) returns true if the input size q - p + 1 is small enough so that the answer can be computed without splitting. If so, the function compute() is invoked. Otherwise the function divide (p, q) is called. This function returns an integer which specifies where the input is to be split.

Let m = divide(p, q). The input is split so that input(p, m) and input(m+1, q) define instances of two subproblems. The subsolutions x and y respectively of these two subproblems are obtained by recursive application of solve(). 

The combine(x, y) is a function which determines the solution to input[p, q] using the solutions x and y to the subproblems input[p, m] and input[m+1, q]. If the sizes of the two subproblems are approximately equal then the computing time of solve() is naturally described by the recurrence relation:

```sh
T(n) = compute(n), n small
       2T(n/2) + f(n), otherwise
```
	   
T(n) - Time for solve() on n inputs.
compute(n) - Time to compute the answer directly for small inputs
f(n) - Time for divide and combine

<blockquote class="note">
  <strong>TIP</strong> 
  <p>
    Recurrence relations will often arise for divide and conquer based algorithms.
  </p>
</blockquote>

For divide and conquer based algorithms which produce subproblems of the same type as the original problem it is natural to first describe such an algorithm using recursion. But to gain efficiency it may be desirable to translate the resulting program into iterative form. 

### Iterative Program Template

The iterative form of divide and conquer program template:

```ruby
def solve(p, q)
  /* declare a stack of appropriate size */
  /* set the stack to empty */
  top = Stack.new
  
  while(!small(p, q))
    m = divide(p, q)
  end
  while top != 0
    /* decrement top  */
    /* process the second recursive call */
    /* combine two solutions into one */
  end
end
```
