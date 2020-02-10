---
layout: post
title: Mental Model in Programming
---

A mental model is a representation of some domain that supports understanding, reasoning, and prediction. Mental models permit reasoning about situations not directly experienced. They allow people to mentally simulate the behavior of a system. 

For instance, the knowledge about the computer memory and how it is used during the program execution can be visualized as shown in the diagram. This is a useful mental model when solving coding problems. Because, we are able to make the design choices.

![Computer Memory](/assets/images/computer-memory-layout.jpg)

Von Neumann Computer Architecture provides a simplified model of a computer for most of the programming tasks.

## Why Mental Models?

- Can reason about the code and analyze the time and space complexity.
- Can make coding decisions using the mental model.
- Can be used to identify the gaps or misunderstandings about current knowledge.

## Simple and Complex Mental Models

Simpler mental models are sufficient for beginner level coding problems. Simpler mental models break as the difficulty of the coding problem increases. Complex mental models are required that either adds more details to existing simpler mental models or replace them with complex mental models to solve complex and difficult problems. 

For instance, recursion is a difficult topic for beginners to understand. Experts have the mental model to understand recursion deeply and they are able to choose between tail recursion or head recursion based on the problem. They know about the system stack, frames for the procedure calls and how the values of variables are bound to the recursive calls.

As programmers we can visualize the data structures and algorithms to reason, understand and predict the behavior of a program. Expert programmers organize their programming knowledge in sophisticated, flexible and viable mental models. They organize their representations of code segments into larger conceptual-programming structures according to the function performed by the code. They form abstract representations based upon the purpose of the code. 

## Design Simulation

On their own, design diagrams remain passive abstractions. This is why experts draw examples alongside the diagrams when they simulate a design. Externalizing their thoughts, juxtaposing the simulation with their design and envisioning the execution in context, forces them to interpret what they drew and to test their design more thoroughly in the process.

### Visualizing Data Structure

If you can draw a diagram of the data structure and have the knowledge about the data structure, we can translate it into code. We can also manipulate the elements in the data structure and write code if we can visualize the data manipulation in the data structure.

For instance, if you can draw a linked list and understand the concept of nodes and links, you can represent those concepts in code. You can also write code for removing or adding a new node by looking at the before and after pictures of the data structure.

## Mental Model of a Variable

### Mathematics and Variable

In mathematics, a variable is an unknown which can take on all the numerical values in a predetermined set. In programming languages, it is necessary to specify this concept in more detail because the model for variables depends on the programming paradigm. 

### Imperative Programming Paradigm and Variable

The classical imperative paradigm uses modifiable variables. According to this model, the variable is seen as sort of container or location that refers to physical memory. We can give a name to the variable and it can contain values. These values can be changed over time, by execution of assignment commands.

![Mental Model of a Variable](/assets/images/mental-model-variable.png)

A programming newbie will have a simple mental model for a variable.

In mathematics, a variable represents a value that is unknown but when such a value is defined the link thus created cannot be modified later.

We can represent a variable with the name x with a box that is filled with a value. It can be seen that the variable (the box) is different from the name x which denotes it. 

![Variable Representation](/assets/images/variable.png)

### Object Oriented Languages and Variable

Some object-oriented languages use a different model. According to this alternative model, a variable is not a container for a value but is a reference to a value which is typically stored in the heap. 

### Functional Languages and Variable

Pure functional languages use a concept of variable similar to the mathematical one: a variable is nothing more than an identifier that stands for a value. Functional languages do not have any modifiable variables.

Assignment is the basic command that allows the modification of the values associated with modifiable variables. It also modifies the state in imperative languages.

## Applying the Mental Model

Expert programmers have the knowledge to understand the meaning behind an innocent looking statement such as an assignment. They have a good grasp of concepts such as the system stack and heap. They know how to make memory management decisions. They know whether to allocate memory dynamically or static memory is sufficient for a given problem. 

This is important in some languages like C/C++ where the memory management is not hidden from a programmer.
