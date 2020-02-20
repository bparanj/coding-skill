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

Recursion can also be single, when the method calls itself once or multiple, when the method calls itself multiple times.

Notice that the method does not return a value in the inductive step, it returns a function instead. Each time a procedure is activated recursively, a new set of local, bound variables is created. Although they have the same names as their corresponding elements in the set local to the previous instance of the procedure, their values are distinct.

## Stack Depth

Normally, a computer allocates two areas of memory for a program: the stack and the heap.

The stack is used to store information about method calls. When a piece of code calls a method, information about the call is placed on the stack. When the method returns, that information is popped off the stack, so the program can resume execution just after the point where it called the method. 

The list of methods that were called to get to a particular point of execution is called the call stack.

The heap is another piece of memory that the program can use to create variables and perform calculations.

Typically, the stack is much smaller than the heap. The stack usually is large enough for normal programs because your code typically doesn’t include methods calling other methods to a very great depth. However, recursive algorithms can sometimes create extremely deep call stacks and exhaust the stack space, causing the program to crash.

The article [Recursion Basics]({% post_url 2019-03-28-recursion-basics %}) has a section on _Removing Recursion_ that explains how you can prevent this kind of deep recursion from exhausting the stack space and crashing the program.

For this reason, it’s important to evaluate the maximum depth of recursion that a recursive algorithm requires in addition to studying its run time and memory requirements.

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

If the recursive call is made before the function performs its own task, then it is called Head Recursion. 

Tail recursion occurs when the last thing a singly recursive algorithm does before returning is call itself.

For example, consider the following implementation of the Factorial algorithm:

```
Integer: Factorial(Integer: n)
      If (n == 0) Then Return 1
      Integer: result = n * Factorial(n - 1)
      Return result
  End Factorial
```

The algorithm starts by checking to see whether it needs to call itself recur- sively or whether it can simply return the value 1. If the algorithm must call itself, it does so, multiplies the returned result by n, and returns the result.

You can convert this recursive version of the algorithm into a nonrecursive version by using a loop. Within the loop, the algorithm performs whatever tasks the original algorithm did.

Before the end of the loop, the algorithm should set its parameters to the values they had during the recursive call. If the algorithm returns a value, as the Factorial algorithm does, you need to create a variable to keep track of the return value.

When the loop repeats, the parameters are set for the recursive call, so the algorithm does whatever the recursive call did.

The loop should end when the condition occurs that originally ended the recursion.

For the Factorial algorithm, the stopping condition is:

```
n == 0
```

so that condition controls the loop. When the algorithm calls itself recursively, it decreases its parameter n by 1, so the non-recursive version should also decrease n by 1 before the end of the loop.

The following pseudocode shows the new nonrecursive version of the Factorial algorithm:

```
Integer: Factorial(Integer: n)
      // Make a variable to keep track of the returned value.
      // Initialize it to 1 so we can multiply it by returned results.
      // (The result is 1 if we do not enter the loop at all.)
      Integer: result = 1
      // Start a loop controlled by the recursion stopping condition.
      While (n != 0)
          // Save the result from this "recursive" call.
          result = result * n
          // Prepare for "recursion."
n=n- 1 Loop
      // Return the accumulated result.
      Return result
  End Factorial
```

This algorithm looks a lot longer than it really is because of all the comments.

Removing tail recursion is straightforward enough that some compilers can do it automatically to reduce stack space requirements.

Of course, the problem with the Factorial algorithm isn’t the depth of recursion, it’s the fact that the results become too big to store in data types of fixed size.

<blockquote class="note">
  <strong>TIP</strong> 
  <p>
    A tail recursion is very easy to re-write in the form of a loop. 
  </p>
</blockquote>

Tail-recursive functions can always be translated directly into iterative functions. The reason is that when we do the tail call, we are effectively replacing the current copy of the function with a new copy with new arguments. We can reuse the parent copy by assigning new values to its arguments and jumping back to the top of the function.

## When Not to Use Recursion

Recursive algorithms are particularly appropriate when the underlying problem or the data to be treated are defined in recursive terms. This does not mean that such recursive definitions guarantee that a recursive algorithm is the best way to solve the problem. 

<blockquote class="note">
  <strong>TIP</strong> 
  <p>
    If there is only one single recursive call either at the end or the beginning, then we must avoid using recursion.
  </p>
</blockquote>

Every recursive program can be transformed into an iterative one. This involves the explicit handling of a recursion stack and these operations will often obscure the essence of a program to such an extent that it becomes difficult to comprehend.

Algorithms which by their nature are recursive rather than iterative should be formulated as recursive procedures. A good example is QuickSort.

We can use recursion in cases the underlying data structures let the choice of recursive solutions appear obvious and natural.

For example, trees are naturally recursive because branches divide into smaller branches that divide into still smaller branches and so on. For that reason, algorithms that build, draw, and search trees are often recursive.

Some problems are naturally recursive. They have a structure that allows a recursive algorithm to easily keep track of its progress and find a solution. 

<blockquote class="note">
  <strong>TIP</strong> 
  <p>
    Recursive algorithms are appropriate when the problem to be solved, or the function to be computed, or the data structure to be processed are already defined in recursive terms.
  </p>
</blockquote>
