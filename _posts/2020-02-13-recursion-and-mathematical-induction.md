---
layout: post
title: Recursion and Mathematical Induction
excerpt: Recursion and Mathematical Induction are closely related concepts. This article looks at how they are related. These are the notes from the paper Computational Recursion and Mathematical Induction by Uri Leron, Rina Zazkis.
---

A good way to learn mathematical induction is to
tackle a problem that admits naturally of an inductive solution. Take for example the problem of how many regions are formed in the plane by n straight lines. Assume no two lines are parallel and no three are concurrent. Since the answer is difficult to see directly from the problem, there is need for investigating.

What is the answer for one line? Two lines? And so on. From here on the investigation may branch into two main routes. The more common one is to look for a pattern in the cases investigated (e g., by arranging the results in a table) and generalize This way one comes to perceive the answer but not the reasons for it. 

The second route is to look for a pattern not merely in the sequence of numbers, but in the way they are generated. Rather than the original question: 

- How many regions for n lines? 

We switch our attention slightly but significantly to the question: 

- How many more regions are generated by the addition of one more line? 

This is where [inductive thinking]({% post_url 2019-06-20-thinking-recursively %}) begins. This approach is very powerful and potentially very satisfying, for it leads to perceiving the answer as well as the reasons for it, so that it can lead to the feeling that one has really understood the solution. 

Didactically, we would tackle this revised question starting with small numbers, and watch for the emerging pattern as we gradually increase n. 

Thus suppose we already have 3 lines. How many new regions are formed by adding a fourth line? Can you do that without counting the regions? We would then repeat for 4, 5, etc, until the class is bored. 

This boredom is welcome and can be put to good use, for what it expresses - "why do we keep playing the same game over and over?" - is what we are after. 

From here, the final step of playing the same game once and for all is not too big to take. That is, we can give the general argument for going from n lines to n + 1 lines even though we do not know the answer for n.

Thus, to summarize, mathematical induction captures the pattern of the argument as we go up from one number to its successor. 

Reference: Computational Recursion and Mathematical Induction by Uri Leron, Rina Zazkis