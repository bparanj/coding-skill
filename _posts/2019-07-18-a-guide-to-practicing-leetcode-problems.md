---
layout: post
title: A Guide to Practicing Leetcode Problems
---

This guide answers questions people often have about interview coding problems and things to watch out.

## List of Topics You Need To Know Well

### Fundamentals of Computers 

Just a general knowing how computers store information etc. Knowing how binary works, how memory is managed in a program (stack & heap), etc.

### Big O Time & Space Complexity Computation

Know asymptotic bounds. If you can be flexible in how you analyze a solution you come up with (lower bounding it, upper bounding, exact bounding) it can help you see whether you can do better and make an improved algorithm

### Array

Often questions that work within arrays will be solved in linear time for the most part. The linear time solution will be tricky.

### Primitives

Things like bit shifting. This is more rare and I don't think this is as important since it doesn't test real thinking abilities since it mixes with one's abilities to bit shift which is an esoteric skill.

### String

These are problems that often deal with strings like permutations, backtracking problems that have use take an exhaustive approach in producing decompositions of a string to search a possibility space (which is often a brute force way of solving a problem since it will be exponential in time), etc. String problems are often solved most optimally in O(n) time or O(s1 + s2) time (linear with respect to each string) if we are given two strings.

### Dynamic Programming

One of the most difficult subjects. Subproblems is the key. If you can identify the subproblem, you have cracked the problem. Because from there it is all about memoization to cache and leverage previous solutions.

### Recursion / Backtracking

At some point you will naturally think of solutions in a recursive manner (if backtracking could be a possible approach used). Problems that use backtracking often say: "generate all", "compute every". This indicates an expression of exhaustively expressing all the possibilities of a decision space. Recursion is beautiful for this type of problem.

### Graph

Know DFS and BFS. DFS uses a stack (either implicit with the call stack and recursion or explicit if we create our own stack) and BFS uses a queue.

### Greedy Algorithms

These are algorithms that take the locally most optimal solution to achieve a global optimal. In contrast to problems that use dynamic programming (which is characterized by caching previous subproblems to find a global optimum), greedy algorithms take locally optimal choices.

Not all greedy approaches one comes up with will work 100% of the time so it hinges on being able to use deductive logic to prove that a given approach will always work

### Hashtables

Very common in mid-level interviews. This is a must know. It is simple, when our time complexity is too high, we can often reduce time and increase space by using some sort of auxiliary structure to cache work. Hashtables are often that auxiliary structure.

### Linked Lists

A tricky structure to work with. It is hard because we can't index into items. It gets easier with time but always remains tricky.

### Sorting

Know the fundamental sorting algorithms. Bubble, Insertion, Selection, Merge, Quick, Heap, etc.

### Searching

If an array is sorted. Immediately know that that is a strong hint that the optimal solution will use binary search and stay to the order of O(log(n)).

### Min/Max Heaps

If you see: "find the largest" or "find the smallest", anything to do with size, think heap. Min or max. If we want larger items we use a min heap since we can throw away small items (to leave the large ones behind). And vice versa for when we want the smaller items.

### Stack

LIFO structures. Know how to implement a stack inside out. I'd suggest knowing how to implement all data structures stated here. 

### Queue

FIFO structures. Used for Breadth First Search.

### Tree, Binary Tree & Binary Search Tree

Trees are connected, acyclic, graphs. You can do DFS and BFS on them. Print all the characters in the tree in this order. Does it look like DFS? Traverse the tree level by level? Looks like BFS. BFS goes out level by level.

## An Approach To Preparation

1. Find your weak topics. 

2. Start with easy problems. 

3. Easy problems will be very difficult when you just start. Then they will start getting easy. Then move onto the medium level difficulty problems.

4. Summer internship interviews will be medium difficulty questions. Full-time roles will be upper medium questions sprinkled with a few hard questions. Stay rooted in the fundamentals above and you can survive.

5. Go onto hard problems if you want. But don't get lost on esoteric problems that require special tricks. This is all about getting ready to pass an interview for a job, not about bragging rights.

6. Top it all off with polishing your delivery. Take mock interviews.

## How Many Leetcode Problems Until I am Ready?

There is no finite amount. Every person comes to the table with their own weaknesses in all topics above. You will know when you are ready. You will see a problem and say: "Oh...yeah I know what principle to apply here". The more you get that spark, the higher the chances you pass.

### Practice Strategically

It is a good strategy to pick few questions from different topics in algorithm and data structures rather than thinking of exhaustively solving all questions of one topic first. Check out the Leetcode learn section that can help you pick topics to get started.

## Should I Time Myself?

Time is critical. Speed is critical. But timing yourself is useless if you are very uncomfortable with a specific problem class. I suggest solving many problems (peeping the solutions often is fine, just gain comfort) in your weak points. Then when you get sick of jumping to answers you will soon take the leap and just solve the problem yourself because you will become familiar with the techniques required for the approach. This is how backtracking was for me. I went from total confusion to it becoming a default way of thinking.

### Track Time 

Once you are familiar with a specific problem class, try to track how much time you spend on each question. You should also have a limit on how much time you will spend on a single question. As you keep practicing, you can keep decreasing your limit and effectively increase the number of questions.

## What Should I focus My Study On?

Weak points. And then popular problems. Find a list of problems the company you are interviewing at asks. No idea whether this is a myth or not (and CTCI addressed this as false, that companies repeat questions from a list) but I have friends that told me of getting exactly questions from these lists. It isn't critical but it can help.

### Practice Strategically

It is a good strategy to pick few questions from different topics in algorithm and DS rather than thinking of exhaustively solving all questions of one topic first. Check out the Leetcode learn section that can help you pick topics to get started.

## Reading Books vs. Leetcode/HackerRank

Books give you theory. Coding gives you the memory in your fingers and the necessary practice. Like if I know a problem will use BFS, how fast can I put the logic in place for a basic search? If I know that a problem may use a heap, how fast can I throw up a priority queue with the right comparator (if it is a max or min heap. Java defaults to a min heap without a comparator)

## Gather Advice

Technical interviews vary based on the employer and even the interviewer. Spend time exploring tips from companies like Google and Microsoft to figure out what matters most. Talk to you professionals working those companies to learn from their mistakes and success. A useful resource for that: [RESOURCE LINK GOES HERE]

