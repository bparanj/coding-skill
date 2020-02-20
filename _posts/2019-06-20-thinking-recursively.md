---
layout: post
title: How to Think Recursively
---

In this article, we will look at some example problems and solve it recursively and iteratively. Sometimes it is possible to define an algorithm in terms of itself. This process is called recursion. It is similar to mathematical induction.

<blockquote class="note">
  <strong>MATHEMATICAL INDUCTION</strong> 
  <p>
    Mathematical induction is an important proof technique used in mathematics. Mathematical induction proof consists of two steps and these are the base step and the inductive step.
  </p>
</blockquote>

The article [Recursion and Mathematical Induction]({% post_url 2020-02-13-recursion-and-mathematical-induction %}) explains how they are related to each other in more detail.

## Algorithmically

Recursion is a way to design solutions to problems by [Divide and Conquer]({% post_url 2019-04-04-divide-and-conquer %}) or decrease-and-conquer. Reduce a problem to simpler versions of the same problem.

## Semantically

Recursion is a programming technique where a function calls itself. The solutions has one or more base cases that are easy to solve. Must solve the same problem on some other input with the goal of simplifying the larger problem input.

Notice that the method does not return a value in the inductive step, it returns a function instead. The values of the new function that is returned has smaller data that gradually moves the program towards the base case.

## Summation

A recursive function is a function that is defined by itself or that calls itself. The sum function is given as an example, which is defined as follows:

```
sum(n) = 1 + 2 + ... + n
```

That means, the first n natural numbers are added. So, for n = 4 we get:

```
sum(4) = 1 + 2 + 3 + 4 = 10
```

If we want to calculate the result of the sum function for a certain n and we already know the result for n - 1, n just has to be added to this result:

```
sum(n) = sum(n-1) + n
```

Such a definition is called a recursive step. In order to calculate the sum function for some n in this way, we still need the base case for the smallest n:

```
sum(1) = 1
```

Using these definitions, we are now able to calculate the sum function for some n:

```
sum(4) = sum(3) + 4
       = (sum(2) + 3) + 4
	   = ((sum(1) + 2) + 3) + 4
	   = ((1 + 2) + 3) + 4
	   = 10
```

We can implement this in code. Here is the C language function to compute sum of first n positive numbers:

```c
int sum(unsigned int n) {
  if (n == 0)
    return 0;

  if (n == 1)
    return 1;

  return n + sum(n-1);
}
```

You can see the last line that makes the recursive call is using the same form we saw earlier:

```
sum(n) = sum(n-1) + n
```

<blockquote class="note">
  <strong>STACK OVERFLOW</strong> 
  <p>
    If you miss the base case, the function will get into an infinite recursion causing the stack overflow error.
  </p>
</blockquote>

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

```python
mult(a, b)
  result = 0
  while b > 0
    result += a
    b -= 1
  return result
```

<blockquote class="note">
  <strong>RECURSIVE THINKING</strong> 
  <p>
    It is not natural for human mind to think recursively. Recursion and mathematical induction are based on the same idea. Think of recursion as an executable version of induction. When programming recursively, think inductively.
  </p>
</blockquote>

## Exponent

### Problem Statement

Compute the n<sup>th</sup> power of a number X<sup>n</sup>.

### Mathematical Definition

The mathematical function is defined as follows:

For n = 0, X<sup>n</sup> = 1

Otherwise if n > 0 X<sup>n</sup> = X * X<sup>n-1</sup>

### Program

The C implementation of exponentiation:

```c
int power(int x, int n) {
  if (0 == n)
    return 1;
  else if (1 == x)
    return x;
  else
    return x * power(x, n-1);
}
```

<blockquote class="note">
  <strong>TIME AND MEMORY</strong> 
  <p>
    The recursive solution takes more time and more memory than the corresponding iterative solution.
  </p>
</blockquote>

In situations where both iterative and recursive solutions are equally easy to code, choose iterative solution. The advantage of recursion is that sometimes a solution that is very complex to understand can be easily visualized recursively. We just need to solve the problem for the base case and leave the rest of the problem to be solved by recursion. Tower of Hanoi problem is an example.

## Head Recursion and Tail Recursion

If the recursive call is made before the function performs its own task, then it is called Head Recursion. If recursive call is made at the end, then it is Tail Recursion.

<blockquote class="note">
  <strong>TIP</strong> 
  <p>
    A tail recursion is very easy to re-write in the form of a loop. 
  </p>
</blockquote>

Tail-recursive functions can always be translated directly into iterative functions. The reason is that when we do the tail call, we are effectively replacing the current copy of the function with a new copy with new arguments. We can reuse the parent copy by assigning new values to its arguments and jumping back to the top of the function.
