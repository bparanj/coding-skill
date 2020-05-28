---
layout: post
title: Choice of Datastructure for N Queens Problem
excerpt: Why is not a good idea to choose matrix as the data structure for N Queens problem?
---

It's a waste of space, and introduces unnecessary degrees of freedom that may inflate the search space.

A solution to the N Queens problem, N=8, in a 2-dimensional matrix, might be represented as:

```
0 0 1 0 0 0 0 0
0 0 0 0 0 1 0 0
0 0 0 0 0 0 0 1
1 0 0 0 0 0 0 0
0 0 0 1 0 0 0 0
0 0 0 0 0 0 1 0
0 0 0 0 1 0 0 0
0 1 0 0 0 0 0 0
```

In order to find a solution to N-Queens using the matrix as our representation, we may have to consider all n x n matrices that have n 1s. The number of such matrices is:

$$\binom{n^2}{k}$$

which, for N=8 is:

$$\binom{68}{8} = 4426165368$$

By contrast, the same solution could be represented as a permutation of the columns 1 - N, with the interpretation that the first column listed has a queen in the first row, the second column listed has a queen in the second row, and so on. This works because the rules of the puzzle guarantee that no solution will put two queens on the same column or the same row. The same solution for the N=8 problem would be represented as:

```ruby
[3, 6, 8, 1, 4, 7, 5, 2]
```

Since all possible solutions correspond to some permutations of the N columns, there are only `n!` possible solutions to consider. For N=8, that's:

```
8! = 40320
```

In comparison, the matrix representation leads to a very inefficient representation of the search space.


