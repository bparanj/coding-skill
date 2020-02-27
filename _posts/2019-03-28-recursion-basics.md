---
layout: post
title: Recursion Basics
---

In this article, we will cover the basics of recursion with a few examples. We will see how to translate recursion into an iterative equivalent.

### Recursion

Recursion makes it possible to solve complex problems using programs that are concise and easily understood. It requires thinking about problems in a new and different way. 

Recursion is the process of solving a large problem by reducing it to one or more subproblems which are:

1. Identical in structure to the original problem.
2. Somewhat simpler to solve.

Once that original subdivision has been made, the decompositional technique is used to divide each of these subproblems into new ones which are even less complex. Eventually the subproblems become so simple that they can be then solved without further subdivision and the complete solution is obtained by reassembling the solved components.

The only thing that changes is the dimension of the problem. The essence of the recursive approach lies in applying the same decomposition repeatedly at each stage of the solution.

Solutions which operate in this way are referred to as Divide and Conquer strategies. Since they depend on splitting a problem into more manageable components. 

The original problem divides to form several simpler subproblems, which, in turn, branch into a set of simpler ones and so on, until the simple cases are reached. If we represent this process diagrammatically, we obtain a solution tree for the problem.

In order to represent this algorithm in a form more suggestive of a programming language, it is important to notice that there are several different instances of a similar problem.

### Recursive Program Structure

There is a structural similarity of each problem. To exploit that similarity, we must first generalize the problem.

```ruby
def solve(n)
  if simple?
    # Compute the value
  else
    # 1. Problem is divided into subproblems
    # 2. Solve by recursive strategy
  end
end
```

The structure of this program is typical of recursive algorithms represented in a programming language. Many recursive programs share this underlying structure. 

The first step in a recursive procedure consists of a test to determine whether or not the current problem represents a simple case. If it does, the procedure handles it directly. If not, the problem is divided into subproblems, each of which is solved by applying the same recursive strategy.

### Characteristics of Recursive Algorithms

To be an appropriate candidate for recursive solution, a problem must have three distinct properties:

1. It must be possible to decompose the orginal problem into simpler instances of the same problem.

2. Once each of these simper subproblems has been solved, it must be possible to combine these solutions to produce a solution to the original problem.

3. As the large problem is broken down into successively less complex ones, those subproblems must eventually become so simple that they can be solved without furthur subdivision.

The first step consists of checking to see if the problem fits into the simple case category. If it does, the problem is solved directly. If not, the entire problem is broken down into new subsidiary problems, each of which is solved by a recursive application of the algorithm. Finally, each of these solutions is then reassembled to form the solution to the original problem.

### Recursive Program Template

```ruby
def solve(instance)
  if instance_is_easy
    # solve problem directly
  else
    # 1. Break it into new instances I1, I2, etc
    # 2. solve(I1), solve(I2) and so forth...
    # 3. Reassemble the solutions
  end
end
```

### Simplify and Delegate

Recursion is a powerful programming technique. We discussed reduction in the article [Problem Solving Techniques for Coding Interview]({% post_url 2020-01-23-problem-solving-techniques-for-coding-interview %}).

Recursion is a powerful kind of reduction, which can be described as follows:

- If the given instance of the problem can be solved directly, solve it directly.
- Otherwise, reduce it to one or more simpler instances of the same problem

Your only task is to simplify the original problem or to solve it directly when simplification is either unnecessary or impossible.

Eventually, the recursive reductions must lead to an elementary base case that can be solved by some other method. 

Otherwise, the recursive algorithm will loop forever. The most common way to satisfy this condition is to reduce to one or more smaller instances of the same problem. So the sequence of smaller problems must eventually converge on the base case.

### Why Recursion?

The principal advantage of recursion as a solution technique is that it provides an excellent mechanism for managing complexity. Now matter how difficult a problem at first appears, if we can determine a way to break that problem down into simpler problems of the same form, we can define a strategy for producing a complete solution. 

As programmers, all we need to specify is:

1. How to simplify a problem by recursive subdivision.
2. How to solve the simple cases.
3. How to reassemble the partial solutions.

Writing a recursive programs requires a holistic view of the process. It is the big picture which is important, not the details. In developing a recursive instinct, you must stop analyzing the process after the first decomposition. The rest of the problem will take care of itself. The details will confuse the issue.

Recursive code is generally concise and easy to write than iterative equivalent. Recursion is most useful for tasks than can be defined in terms of similar subtasks. For example, sort, search and traversal problems often have simple recursive solutions.

### Recursion and Memory

Each recursive call makes a new copy of that method in memory. Once a method ends and returns some data, the copy of that returning method is removed from memory.

### Fibonacci Sequence

Now, let's take look at a few examples. The Fibonacci sequence 1,1,2,3,5,8,13,21,34 is defined as:

![Fibonacci Sequence](/assets/images/fibonacci.png)

This mathematical definition naturally leads to the recursive procedure:

```ruby
def f(n)
  return n if n <= 1
  return f(n-1) + f(n-2)
end
```

The virtue of this program is that it is almost syntactically identical to the mathematical definition. However it is inefficient from the standpoint of computing time. 

The time complexity of this solution is O(2<sup>n</sup>). The major source of the inefficiency is not because of recursion. The reason is that many values are recomputed many times. For example, f(n-2) is computed twice, f(n-3) is computed three times and f(n-4) is computed five times. 

<blockquote class="note">
  <strong>DYNAMIC PROGRAMMING</strong> 
  <p>
    If a calculation such as the Fibonacci numbers must recalculate the same values many times, you can save time by storing values in a lookup table so that you need to calculate them only once.
  </p>
</blockquote>

Applying dynamic programming to Fibonacci sequence solution improves the performance from exponential to O(n).

#### Greatest Common Divisor 

The greatest common divisor (GCD) of two integers is the largest integer that evenly divides both of the numbers. For example, GCD(60, 24) is 12 because 12 is the largest integer that evenly divides both 60 and 24.

Compute the GCD of two nonnegative integers. Given 22 and 8, we compute gcd as follows:

```
gcd(22,8) = gcd(8,6) = gcd(6,2) = gcd(2,0) = 2
```

The GCD of 21 and 13 is computed as follows:

```
gcd(21, 13) = gcd(13,8) = gcd(8,5) = gcd(5,3) = gcd(3,2) = gcd(2,1) = gcd(1,0) = 1
```

<blockquote class="note">
  <strong>MODULUS OPERATOR</strong> 
  <p>
    The modulus operator, which is written as % (percent symbol) in Ruby, means the remainder after division. For example, 13 % 4 is 1 because 13 divided by 4 is 3 with a remainder of 1.
  </p>
</blockquote>

We begin by computing 21 mod 13. This gives us 8 as the result. You can observe that b becomes a and we again compute 13 mod 8 and so on. 

```
 > 21 % 13
 => 8
 > 13 % 8
 => 5
 > 8 % 5
 => 3
 > 5 % 3
 => 2
 > 3 % 2
 => 1
 > 2 % 1
 => 0 
``` 

Expressing this process as a recursive procedure one gets:

```ruby
def gcd(a, b)
  return a if b == 0

  gcd(b, a % b)
end
```

Recursion can be used for problems that are not mathematical functions. For instance, we can search for a given number in an array by using recursion. By using recursion the need for a looping statement is removed.

### Recursion vs Iteration

A recursive approach mirrors the problem that we are solving. A recursive approach makes it simpler to solve a problem that may not be obvious to solve. But recursion incurs overhead for each recursive call. Because it needs space on the stack frame.

If we get infinite recursion, the program will run out of memory and result in stack overflow error. Any problem that can be solved recursively can also be solved iteratively. 

A recursive algorithm can be translated to its iterative equivalent using a stack, but it's usually more trouble than its worth.

### Removing Recursion

Some design techniques are inherently recursive and so recursion is a natural way to describe algorithms obtained from these techniques. 

Recursion incurs overhead of repeated procedure calls. In the early stages of algorithm design we can use recursion. Once we are satisfied that we have a good algorithm, the recursion can be removed by translating the algorithm into an equivalent one that uses iteration. 

Translating a recursive procedure into an equivalent procedure which uses iteration involves replacing all recursive procedure calls and return statements by equivalent non-recursive code.

<blockquote class="note">
  <strong>GENERAL RECURSION REMOVAL</strong> 
  <p>
    You can remove recursion more generally by mimicking how a program calls a method recursively. Push variables onto stacks before recursion, and pop them off afterward.
  </p>
</blockquote>

At the beginning of the procedure, code is inserted which declares a stack and initializes it to be empty. In the most general case, the stack will be used to hold the values of parameters, local variables, function value and return address for each recursive call.

The rules are for the general case. Often there are occasions when simpler rules apply. For example if the last statement of a procedure is a recursive call, then remove it by simply evaluating the new values of the parameters and branching to the beginning. A stack is not needed. 

The gcd procedure is an example. Removing its recursion yields the following program:

```ruby
def gcd(a, b)
  while b != 0
    t = b
    b = a % b
    a = t
  end
  return a
end
```

The objective of removing recursion is to produce a more efficient but computationally equivalent iterative program. In some languages the compiler translates recursive procedures into efficient code.

Sometimes, you can remove recursion by starting with the smallest pieces of data and using them to build larger ones rather than starting at the largest scale and recursively dividing the data. This is called Bottom-up programming.

<blockquote class="note">
  <strong>WHEN TO USE RECURSION</strong> 
  <p>
    The class of backtracking algorithms emerges as an ideal application of recursion, but the most obvious candidates for the use of recursion are algorithms operating on data whose structure is defined recursively.
  </p>
</blockquote>
