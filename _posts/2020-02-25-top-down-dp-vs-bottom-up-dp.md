---
layout: post
title: Bottom Up Dynamic Programming vs Top Down Dynamic Programming
excerpt: What is the difference between bottom up dynamic programming and top down dynamic programming?
---

In bottom up Dynamic Programming algorithm, for example with Fibonacci:

1. Memoize
2. Go from smaller to larger value of n.

We always go from smaller to larger value for Bottom Up DP and larger to smaller values for Top Down DP. With top down recursion is that we go from bigger values to smaller values till we hit the base case. Let's consider both approaches for finding fibonacci.

## Top Down Dynamic Programming

```python
F = []
FIBONACCI(n)
  if F[n] == null
    if n==0 //base case
      F[n] = 0
    else if n==1 //base case
      F[n] = 1
    else
      F[n] = FIBONACCI(n-1) + FIBONACCI(n-2)
  return F[n]
```

Now in this algorithm you can see that we have made an blank array, and make recursive calls till we reach 0 or 1, when we reach 0 and 1 we fill these values and backfilling starts. This is how top down dynamic programming and recursion works.

## Bottom Up Dynamic Programming

```python
F = []
FIBONACCI(n)
  F[0] = 0 //Initial values
  F[1] = 1 //Initial values

  for i in 2 to n
    F[i] = F[i-1] + F[i-2]

  return F[n]
```

Here you can see that we store initial values first in the array and use then for calculating further values, i.e from smaller values, we calculate bigger values, this is how bottom up dynamic programming works.

And you can keep this as rule that we always go from smaller to larger value for Bottom Up Dynamic Programming and larger values to smaller values for Top Down Dynamic Programming.
