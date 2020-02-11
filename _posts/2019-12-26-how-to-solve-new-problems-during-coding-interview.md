---
layout: post
title: How to Solve New Problems During Coding Interview
excerpt: In this article we will discuss the strategy to use when you have to solve a new problem that you've never solved before.
---

Solving programming problems requires two skills: 

1. The design of algorithms
2. The implementation of algorithms

The design of algorithms consists of problem solving and mathematical thinking. This demands skills for analyzing problems and solving them creatively. An algorithm must be both correct and efficient and the core of the problem is often about inventing an efficient algorithm. 

Theoretical knowledge of algorithms is an important prerequisite to design algorithms. Typically, a solution to a problem is a combination of well-known techniques and new insights. 

The implementation of algorithms requires good programming skills. The solution must be tested using a set of test cases. The implmentation must be correct to pass all the test cases.

Coding style must be straightforward and concise. The programs are short - usually less than 50 lines of code. 

## Approaching the Coding Problem

- Is the problem too vague? Ask more questions.
- Is there a formula to solve this problem? Use math first. Always.
- Can you derive an equation from the problem statement?
- Taking more than O(n log n) time? Consider sorting as an intermediate step to solve the problem.
- Are any superlatives such as least, longest, shortest used? Think Greedy/Dynamic programming.
- Did you see the word 'find' in the problem statement? Consider the hash table.
- Unable to make use of the extra property given? Try solving the problem in reverse. Begin from the end of array, from top-right corner of a matrix.
- Is the input overwhelming? Start with the smallest input and grow.
- Is the problem too hard? See if you can pre-process or rearrange the problem to simplify it.
- Does the problem refuse to die? Just eliminate a part of input at each step.
- Don’t know how to make most operations logarithmic? How many data structures have you studied?

Problem solving is an amalgamation of knowledge about math, data structures, algorithms, practice, intuition and some tricks. Start by learning what has already been invented over several decades.

## Algorithmic Problem Solving

In this article we will discuss the strategy to use to solve a new problem that you've never solved before.

Let's now look at a step by step approach to solving a new problem.

**Step 1 : Clarifications**

The first step is to make sure that you understand the problem. State the problem as you understand it and any assumptions.

- What are the parameters involved? 
- What is the goal for the solution? 

Ask lot of questions. When faced with a hard problem, ask as many questions as you can think of to find the assumptions that is relevant to the solution. 

In this step you determine the scope of the problem. You must understand what you're trying to analyze and solve before moving on to the next step.

**Step 2 : Work Through Examples**

After you've asked a lot of questions to clarify the problem, the next step is to confirm your understanding by working through an example.

Working through an example is useful because it lets you recognize an emerging pattern and provides you the momentum to solve the problem.

This gives you some time to think through the problem very concretely about any difficulties in the solution.

You might also find any hidden assumptions or implicit questions that you need to address again. If so go back to the first step of asking more questions to make sure that you've mapped out the scope of the solution.

Use specific examples to figure out the general solution. Break problems down into steps and explain along the way.

Okay, so at this point we have a very good understanding of the problem and we're ready to solve it.

**Step 3 : First Correct Solution**

In the next step we come up with a first solution. You want to solve the problem, even if it's not a good approach. This is the brute force approach.

This approach does not have to be clever or elegant. But you want to make sure that you've got a correct solution.

If you're stuck, vocalize your thoughts on where exactly you're stuck and maybe ask the interviewer something like "This approach should work right?". 

Usually, they'll guide you the right way. If the interviewers rule out an approach for the presented problem, follow the instructions and try something different. 

When given hints, make sure you respond well and demonstrate your ability to work with others. Being able to respond to a hint is mostly seen as a positive signal.

**Step 4 : Test Your Solution**
 
As you're developing your brute force approach as first naive solution to the problem, the next step is to test it. Test it with normal input as well as edge cases. Your brute-force approach must handle both.

Think through a little bit if you were to implement this first solution: 

- How would you do it? 
- What data structures would be useful? 
- How would those data structures interact with the problem that you're working with? 
- What performance would you get out of this implementation? 

Think about any trade-offs in terms of using more memory to speed up the performance or vice verse. So, we've got a solution. But we didn't spend a lot of time trying to make it clever or elegant.

**Step 5 : Refine Your Solution**

So our next step is to iterate this whole process of coming up with a candidate approach to solving the problem. Evaluating, testing and poking at it, making sure that it works correctly or if it doesn't, thinking about ways to fix it and refine your solution as much as you can.

The interviewer will try to guide you towards iterating your solution, asking you if it could be made better, asking you if there are any trade-offs that you have in mind. 

Think about speed, accuracy and optimality. While optimality is important, make sure you have working code in the given time that completely solves the problem. Always try to build up from a brute force solution that is easy to code. If you end up overcomplicating things by focusing on optimality, try to snap out of it and ensure you have working code to show at the end. 

Remember: working code wins.This shows your coding skills and also allows the interviewer to give hints if there is time left. The best solutions usually require less than 30 lines of code. Always remember to explain the complexity when you are confident you have a solution (without prompting from the interviewer is better).

Now when we iterate, we come up with a great solution, that we think at the high level will do a pretty good job. We've done an asymptotic analysis. We have a sense of how long asymptotically using Big O notation each of the operations involved will take.

**Step 6 : Write Code**

Finally in step 6 we finally write some code. So only after a very thorough analysis of the problem, you have a very good sense of what you want to implement, now you can start writing some code on the whiteboard.

Programming on a white board in the interview situation is quite different from typing it out in a computer. It's a good idea to practice on whiteboard during preparation.

You can download the [Problem Solving Approach PDF](/assets/files/problem-solving-approach.pdf) to use as a guide for your preparation. This is based on a 45 minutes interview with few minutes at the end for asking questions to the interviewer. The article [Tecnical Interview Tips]({% post_url 2019-09-19-technical-interview-tips %}) has suggestions on questions you can ask at the end of the interview.

