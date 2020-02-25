---
layout: post
---

Reduction is the single most common technique used in designing algorithms. Reducing one problem X to another problem Y means to write an algorithm for X that uses an algorithm for Y as a black box. 

A problem A reduces to a problem B, if an algorithm that solves B can be easily translated into one that solves A. For example, the problem of computing the median element of an array reduces to the problem of sorting the array. 

You should always be on the lookout for reductions. Whenever you encounter a seemingly new problem, always ask: 

- Is the problem a disguised version of one you already know how to solve? 
- Can you reduce the general version of the problem to a special case?
- Can you use a problem with a known solution as a subroutine?

<blockquote class="note">
  <strong>TIP</strong> 
  <p>
    You should always be on the lookout for reductions to problems you already know how to solve.
  </p>
</blockquote>

### Shipping Packages

When you send a package by Federal Express from uptown New York City to downtown New York City, the package will be routed through Memphis. Federal Express routes all packages through Memphis, so when they are faced with the special situation of delivering packages across town they "already know how to solve the problem." In this case, the solution makes sense. 

It may be much more difficult to identify a special situation and to build a mechanism to handle that situation more efficiently. It may be easier, and overall cheaper, to handle everything equally. This is also often true in algorithm design. 

### Computing Problems

When we encounter a problem that can be posed as a special case of another problem, whose solution is already known, then the known solution can be used. Such a solution may sometimes be too general or too expensive. But in many cases, using a general solution is the the easiest, the fastest, and the most elegant way to get a solution. We use this principle every day.

For some computing problems for example, a database query it is usually not necessary to write a program that solves only this problem; it is sufficient to use general-purpose software that handles more general problems. The general-purpose solution may not be the most efficient solution, but it is much easier to use.

<blockquote class="note">
  <strong>FINDING NEW TECHNIQUES</strong> 
  <p>
    Finding a reduction between two problems is useful even if it does not lead directly to new upper or lower bounds on the complexity of the problem. The reduction helps us to understand both problems. The reduction may be used to find new techniques for attacking the problem or variations of it. For example, the reduction may be used to design a parallel algorithm for the problem.
  </p>
</blockquote>

#### Ways to Solve Problems
 
Suppose that we are given a problem P that seems complicated, but that also seems similar to a known problem Q. We can try to solve P from scratch, or we can try to borrow some of the methods used to solve Q and apply them to P.

There is, however, a third way. We can try to find a reduction (or transformation) between the two problems. Loosely speaking, a reduction is a solution of one problem using a "black box" that solves the other problem. Reductions can achieve one of two goals depending on the direction in which they are done (i.e.,which black box is used to solve which problem).

A solution of P that uses a black box for Q can be translated into an algorithm for P if we know an algorithm for Q. On the other hand, if P is known to be a hard problem, or, in particular, if we know a lower bound for P, then the same lower bound may be applied to Q. In the former case, the reduction is used to obtain information about P, wherease, in the latter case, it is used to obtain information about Q.

<blockquote class="note">
  <strong>BOTTOM LINE</strong> 
  <p>
		In reduction, we map one problem to another so that we could use a known algorithm.
  </p>
</blockquote>

#### Matrix Multiplication

For example consider the problems of matrix multiplication and matrix squaring (multiplying the matrix with itself). Clearly, we can square a matrix with a matrix multiplication algorithm. Therefore, the problem of matrix squaring can be reduced to the problem of matrix multiplication.

## Conclusion

An effective way to use reductions is to define a general problem to which many problems can be reduced. Finding such a general problem is not easy. This problem should be general enough to cover a wide variety of problems, but it must also be simple enough to have an efficient solution. One such problem is linear programming.