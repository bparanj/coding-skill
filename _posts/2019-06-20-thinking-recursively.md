---
layout: post
title: How to Think Recursively
---

In this article, we will look at multiplication problem and solve it recursevily and iteratively.

## Algorithmically

Recursion is a way to design solutions to problems by divide-and-conquer or decrease-and-conquer. Reduce a problem to simpler versions of the same problem.

## Semantically

Recursion is a programming technique where a function calls itself. The solutions has one or more base cases that are easy to solve. Must solve the same problem on some other input with the goal of simplifying the larger problem input.

## Multiplication
### Recursive Solution

Multiply two numbers using multiplication operator. For instance:

```
5 * 3 = 5 + 5 + 5
```
We add 5, 3 times. This is the same as:

```
5 * 3 = 5 + 5 * (3 - 1)
```

We keep going until we multipy by 1. This is the base case.

```
5 * 3 = 5 + 5 + 5 * (2 - 1)
```

```
5 * 3 = 5 + 5 + 5 * 1
```

We can generalize this as below:


```
a * b = (a + a + a + a + a + a)
```

Add a to itself b times.

```
a * b = (a + a + a + a + a + a) 
		b times
	= a + (a + a + a + a + a)
		b - 1 times
  = a + a * (b-1)
```

The last line: 

```
a + a * (b-1)
```

is called the Recursive Reduction. Notice that the original problem is reduced to a smaller problem that is similar to the original problem.

## Multiplication

### Iterative Solution

```
mult(a, b)
  result = 0
  while b > 0
    result += a
    b -= 1
  return result
```
