---
layout: post
title: Recursion Basics
---

In this article, we will cover the basics of recursion with a few examples. We will see how to translate recursion into a iterative equivalent.

### Recursion

Recursion is a powerful programming technique. We discussed reduction in the article [Problem Solving Techniques for Coding Interview]({% post_url 2020-01-23-problem-solving-techniques-for-coding-interview %})

#### Simplify and Delegate

Recursion is a powerful kind of reduction, which can be described as follows:

- If the given instance of the problem can be solved directly, solve it directly.
- Otherwise, reduce it to one or more simpler instances of the same problem

Your only task is to simplify the original problem or to solve it directly when simplification is either unnecessary or impossible.

Eventually, the recursive reductions must lead to an elementary base case that can be solved by some other method. 

Otherwise, the recursive algorithm will loop forever. The most common way to satisfy this condition is to reduce to one or more smaller instances of the same problem. 

Now, let's take look at a few examples.

#### Fibonacci Example

The Fibonacci sequence 1,1,2,3,5,8,13,21,34 is defined as:

![Fibonacci Sequence](/assets/images/fibonacci.png)

This mathematical definition naturally leads to the recursive procedure:

```ruby
def f(n)
  return n if n <= 1
  return f(n-1) + f(n-2)
end
```

The virtue of this program is that it is almost syntactically identical to the mathematical definition. However it is inefficient from the standpoint of computing time. 

The major source of the inefficiency is not because of recursion. The reason is that many values are recomputed many times. For example, f(n-2) is computed twice, f(n-3) is computed three times and f(n-4) is computed five times. 

#### Greatest Common Divisor Example 

Compute the GCD of two nonnegative integers. Given 22 and 8, we compute gcd as follows:

```
gcd(22,8) = gcd(8,6) = gcd(6,2) = gcd(2,0) = 2
```

The GCD of 21 and 13 is computed as follows:

```
gcd(21, 13) = gcd(13,8) = gcd(8,5) = gcd(5,3) = gcd(3,2) = gcd(2,1) = gcd(1,0) = 1
```

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

### Removing Recursion

Some design techniques are inherently recursive and so recursion is a natural way to describe algorithms obtained from these techniques. 

Recursion incurs overhead of repeated procedure calls. In the early stages of algorithm design we can use recursion. Once we are satisfied that we have a good algorithm, the recursion can be removed by translating the algorithm into an equivalent one that uses iteration. 

<blockquote class="note">
  <strong>TRANSLATING RECURSION TO ITERATION</strong> 
  <p>
    Translating a recursive procedure into an equivalent procedure which uses iteration involves replacing all recursive procedure calls and return statements by equivalent non-recursive code.
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

<blockquote class="note">
  <strong>WHEN TO USE RECURSION</strong> 
  <p>
    The class of backtracking algorithms emerges as an ideal application of recursion, but the most obvious candidates for the use of recursion are algorithms operating on data whose structure is defined recursively.
  </p>
</blockquote>
