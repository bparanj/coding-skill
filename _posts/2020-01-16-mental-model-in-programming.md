---
layout: post
title: Mental Model in Programming
---

A mental model is a representation of some domain that supports understanding, reasoning, and prediction. Mental models permit reasoning about situations not directly experienced. They allow people to mentally simulate the behavior of a system. 

For instance, the knowledge about the computer memory and how it is used during the program execution can be visualized as shown in the diagram. This is a useful mental model when solving coding problems. Because, we are able to make the design choices.

![Computer Memory](https://www.codingskill.net/assets/images/computer-memory-layout.jpg)

Recursion is a difficult topic for beginners to understand. Experts have the mental model to understand recursion deeply and they are able to choose between tail recursion or head recursion based on the problem. They know about the system stack, frames for the procedure calls and how the values of variables are bound to the recursive calls.

As programmers we can visualize the data structures and algorithms to reason, understand and predict the behavior of a program. Expert programmers organize their programming knowledge in sophisticated, flexible and viable mental models. They organize their representations of code segments into larger conceptual-programming structures according to the function performed by the code. They form abstract representations based upon the purpose of the code. 

On their own, design diagrams remain passive abstractions. This is why experts draw examples alongside the diagrams when they simulate a design. Externalizing their thoughts, juxtaposing the simulation with their design and envisioning the execution in context, forces them to interpret what they drew and to test their design more thoroughly in the process.

## Mental Model of a Variable

In mathematics, a variable is an unknown which can take on all the numerical values in a predetermined set.  In programming languages, it is necessary to specify this concept in more detail because the model for variables depends on the programming paradigm. 

The classical imperative paradigm uses modifiable variables. According to this model, the variable is seen as sort of container or location that refers to physical memory. We can give a name to the variable and it can contain values. These values can be changed over time, by execution of assignment commands.

![Mental Model of a Variable](https://www.codingskill.net/assets/images/mental-model-variable.png)

A programming newbie will have a simple mental model for a variable.

In mathematics a variable represents a value that is unknown but when such a value is defined the link thus created cannot be modified later.

We can represent a variable with the name x with a box that is filled with a value. It can be seen that the variable (the box) is different from the name x which denotes it. 

![Variable Representation](https://www.codingskill.net/assets/images/variable.png)

Some object-oriented languages use a different model. According to this alternative model, a variable is not a container for a value but is a reference to a value which is typically stored in the heap. 

Pure functional languages use a concept of variable similar to the mathematical one: a variable is nothing more than an identifier that stands for a value. Functional languages do not have any modifiable variables.

Assignment is the basic command that allows the modification of the values associated with modifiable variables. It also modifies the state in imperative languages.

Expert programmers have the knowledge to understand the meaning behind an innocent looking statement such as an assignment. They have a good grasp of concepts such as the system stack and heap. They know how to make memory management decisions. They know whether to allocate memory dynamically or static memory is sufficient for a given problem. 

