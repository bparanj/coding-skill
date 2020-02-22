---
layout: post
title: A Field Guide to Algorithm Design
---

How do you choose algorithm from your toolbox suitable for tackling a wide range of computational problems? When putting it into practice, you might find the sheer number of algorithms, data structures, and design paradigms daunting. 

When confronted with a new problem, what's the most effective way to put your tools to work? To give you a starting point, here is the typical recipe you can use when you need to understand a new computational problem. Develop your own recipe based on your personal experience.

1. Can you avoid solving the problem from scratch? Is it a disguised version, variant, or special case of a problem that you already know how to solve? For example, can it be reduced to sorting, graph search, or a shortest-path computation? If so, use the fastest algorithm sufficient for solving the problem.

2. Can you simplify the problem by processing the input using a for-free primitive, such as sorting or computing connected components?

3. If you must design a new algorithm from scratch, get calibrated by identifying the line in the sand drawn by the "obvious" solution (such as exhaustive search). Is the running time of the obvious solution already good enough?

4. If the obvious solution is inadequate, brainstorm as many natural greedy algorithms as you can and test them on small examples. Most likely, all will fail. But the ways in which they fail will help you better understand the problem.

5. If there is a natural way to break down the problem into smaller subproblems, how easy would it be to combine their solutions into one for the original problem? If you see how to do it efficiently, proceed with the divide-and-conquer paradigm.

6. Try dynamic programming. Can you argue that a solution must be built up from solutions to smaller subproblems in one of a small number of ways? Can you formulate a recurrence to quickly solve a subproblem given solutions to a modest number of smaller subproblems?

7. In the happy case that you devise a good algorithm for the problem, can you make it even better by deploying the right data structures? Look for significant computations that your algorithm performs over and over again (like lookups or minimum computations). Remember the principle of parsimony: Choose the simplest data structure that supports all the operations required by your algorithm.

8. Can you make your algorithm simpler or faster using randomization? For example, if your algorithm must choose one object among many, what happens when it chooses randomly?

9. If all preceding steps end in failure, contemplate the unfortunate but common possibility that there is no efficient algorithm for your problem. Can you prove that your problem is computationally intractable by reducing a known NP-hard problem to it?

10. Iterate over the algorithm design paradigms again, this time looking for opportunities for fast heuristics (especially with greedy algorithms) and better-than-exhaustive-search exact algorithms (especially with dynamic programming).

**Reference**

- Algorithms Illuminated by Tim Roughgarden