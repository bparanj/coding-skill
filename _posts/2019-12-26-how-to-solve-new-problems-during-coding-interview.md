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

## Algorithmic Problem Solving

In this article we will discuss the strategy to use when you have to solve a new problem that you've never solved before.

Let's now look at a step by step approach to solving a new problem.

**Step 1 : Clarifications**

The first step is to make sure that you understand the problem.

- What are the parameters involved? 
- What is the goal for the solution? 

Your first task is to ask lots of questions. When faced with a hard problem, ask as many questions as you can think of to find the assumptions that is relevant to the solution. In this step you determine the scope of the problem. You must understand what you're trying to analyze and solve before moving on to the next step.

**Step 2 : Work Through Examples**

After you've asked a lot of questions to clarify the problem, the next step is to confirm your understanding by working through an example.

Working through an example is useful because it lets you recognize an emerging pattern and provides you the momentum to solve the problem.

It also lets you take some time and think through the problem very concretely about what difficulties might be involved in the solution. You might also find any hidden assumptions or implicit questions that you need to address again. If so go back to the first step of asking more questions to make sure that you've mapped out the scope of the solution.

Okay, so at this point we have a very good understanding of the problem and we're ready to solve it.

**Step 3 : First Correct Solution**

In the next stage of the strategy we come up with a first solution. You want to solve the problem, even if it's not a good approach. This is the brute force approach.

This approach does not have to be clever or elegant. But you want to make sure that you've got a correct solution.

**Step 4 : Test Your Solution**
 
As you're developing your brute force approach as first naive solution to the problem, the next step is to test it. Test it with normal input as well as edge cases. Your brute-force approach must handle both.

Think through a little bit if you were to implement this first solution: 

- How would you do it? 
- What data structures would be useful? 
- How would those data structures interact with the problem that you're working with? 
- What performance would you get out of this implementation? 

Think about any trade-offs in terms of using more memory to speed up the performance, or vice verse. So, we've got a solution. But we didn't spend a lot of time trying to make it clever or elegant.

**Step 5 : Refine Your Solution**

So our next step of the strategy is to iterate this whole process of coming up with a candidate approach to solving the problem. Evaluating, testing and poking at it, making sure that it works correctly or if it doesn't, thinking about ways to fix it and refine your solution as much as you can.

The interviewer will try to guide you towards iterating your solution, asking you if it could be made better, asking you if there are any trade-offs that you have in mind. And you want to think through this checklist of how you evaluate your strategy at each stage of the problem solving process.

Now when we iterate, we come up with a great solution, that we think at the high level will do a pretty good job. We've done an asymptotic analysis. We have a sense of how long asymptotically using Big O notation each of the operations involved will take.

**Step 6 : Write Code**

Finally in step 6 of our strategy, we finally write some code. So only after a very thorough analysis of the problem, you have a very good sense of what you want to implement, now you can start writing some code on the whiteboard.

Programming on a white board in the interview situation is quite different from typing it out in a computer. It's a good idea to practice on whiteboard during preparation.

You can download the [Problem Solving Approach PDF](/assets/files/problem-solving-approach.pdf) to use as a guide for your preparation. This is based on a 45 minutes interview with few minutes at the end for asking questions to the interviewer. The article [Tecnical Interview Tips]({% post_url 2019-09-19-technical-interview-tips %}) has suggestions on questions you can ask at the end of the interview.

