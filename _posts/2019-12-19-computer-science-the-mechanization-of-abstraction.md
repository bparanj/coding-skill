---
layout: post
title: Computer Science - The Mechanization of Abstraction
---

The book Foundations of Computer Science by Al Aho and Jeff Ullman is available for free download online. This book provided a clear explanation of solving real world problems by applying Computer Science knowledge. It filled a beginner's gap in my knowledge. We have worked with graph in high school, we think of plotting a graph using the x and y axis in a graph paper. But in Computer Science graph means something different. It represents nodes and edges. Here is my notes from the book that resulted in my Aha moment.

## Useful Notes from the Book

**Science of Abstraction**

Computer science is a science of abstraction - creating the right model for thinking about a problem and devising the appropriate mechanizable techniques to solve it.

Computer scientists create abstractions of real-world problems that can be understood by computer users and, at the same time, that can be represented and manipulated inside a computer. 

**Scheduling Exam Problem**

For example, consider the problem of scheduling final examinations for courses. We must assign course exams to time slots so that two courses may have their exams scheduled at the same time slot only if there is no student taking both. How do we model this problem? One approach is to draw a circle called a node for each course and draw a line called an edge connecting two nodes if the corresponding courses have a student in common. The figure suggests a possible picture of five courses. The picture is called a course-conflict graph.

Given the course-conflict graph, we can solve the exam-scheduling problem by repeatedly finding and removing "maximal independent sets" from the graph. You can read the first chapter of Foundations of Computer Science by Al Aho and Jeff Ullman on how this problem can be solved with graph.

**Abstraction**

The term abstraction is used to imply simplification, the replacement of a complex and detailed real-world situation by an understandable model within which we can solve a problem. That is, we abstract away the details whose effect on the solution to a problem is minimal or nonexistent, thereby creating a model that lets us deal with the essence of the problem.

Often, finding a good abstraction can be quite difficult because we are forced to confront the fundamental limitations on the tasks computers can perform and the speed with which computers can perform those tasks.

**Problem Solving Tools**

There are three important problem solving tools:

Data models, the abstractions used to describe problems. We have seen a graph to model the course conflict problem.
Data structures, the programming language constructs used to represent data models. For example, C provides built-in abstractions, such as structures and pointers, that allow us to construct data structures to represent complex abstractions such as graphs.
Algorithms, the techniques used to obtain solutions by manipulating data as represented by the abstractions of a data model, by data structures or by other means.

### Data Models

We meet data models in two contexts. In the context of the problem domain, data models such as the graphs are abstractions used to formulate solutions to problems. In the context of programming languages and computers, for example, C has a data model that includes abstractions such as characters, integers and floating-point numbers. The C data model also includes types such as structures, pointers and functions.

### Data Structures

When the data model of the language in which we are writing a program lacks a built-in representation for the data model of the problem at hand, we must represent the needed data model using the abstractions supported by the language. For this purpose, we study data structures, which are methods for representing in the data model of a programming language abstractions that are not explicit part of that language. 

Different programming languages may have strikingly different data models. For example, unlike C, the language Lisp supports trees directly, and the language Prolog has logic built into its data model. 

### Algorithms

An algorithm is a precise specification of a sequence of steps that can be carried out mechanically. 

There are sorting and searching algorithms that efficiently solves sorting and searching problems. There are many other tricks for solving common problems. These are the tools a computer scientist uses when designing programs. 

We need to know the best ways to perform common tasks and we need to learn the principal techniques for designing good algorithms.

## Conclusion

The book Foundations of Computer Science by Al Aho and Jeff Ullman is a good read. The algorithms textbooks use mathematical notation to describe the algorithms. This approach is not accessible to some developers. Once you realize you can create a model of the problem, you are better equipped with solving it and coming up with a solution that can be implemented by using computers.
