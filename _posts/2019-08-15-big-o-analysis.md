---
layout: post
title: Big O Analysis of Algorithms
---

You need to know how to make time space trade offs when you're solving a coding problem. Learn about the Big O analysis of algorithms. What is O(1) time? What is O(n)? Start analyzing the basic operations on the data structure you're learning in terms of time and space complexity. 

## Time Space Complexity

Big O is the worst-case usage of time or space of a problem in relation to the size of input. For instance, for a tree problem, one would usually assume that the tree is unbalanced and looks like a single branch to evaluate Big O because the single branch often leads to the worst case performance of an algorithm.

![Tree](/assets/images/tree.png)

In the diagram above, for a well-balanced tree (on the left), it may take log(n) time to find node 5 but in the worst-case scenario it would take n time to iterate through every single node in the tree.

There aren't that many types of complexity. We can assume that n indicates the length of the input and implicitly any runtime can be assumed to be multiplied by some constant factor k. O(n) is the same as O(2*n), O(3*n), O(4*n), O(k*n) etc., Here are some common time-space complexities:

### Linear O(n)  

An algorithm is said to run in linear time if the execution time of the algorithm is directly proportional to the input size.

Examples:

1. Array operations like search element, find min, find max etc.
2. Linked list operations like traversal, find min, find max etc.

<blockquote class="note">
  <strong>TIP</strong> 
  <p>
    When we need to traverse all the nodes of a data structure for some task then complexity is no less than O(n).
  </p>
</blockquote>

Most optimal algorithms run in linear time. An easy way to identify this is to determine if you're visiting every node or item once and only once. If you are, it is linear. It doesn't matter how many operations, whether it's 1, 2, 3, or 4 lines of code you're executing per node. You are still doing a constant amount of work per input.

### Constant  O(1) 

Constant time algorithms have a running time independent of the input size. Mathematical formulas have fixed running times and are considered constant time. Examples:

1. Accessing n<sup>th</sup> element of an array.
2. Push and pop of a stack.
3. Enqueue and remove of a queue.
4. Accessing an element of Hash-Table.
5. Bucket sort.

### Logarithmic O(log(n))

An algorithm is said to run in logarithmic time if the execution time of the algorithm is proportional to
the logarithm of the input size. Each step of an algorithm, a significant portion of the input is pruned
out without traversing it. For example, binary search.

Logarithmic algorithms are often seen in trees. It's best to think of logarithmic as the height of the tree. So, a binary search, for instance, often includes traversing down the height of a tree and can be considered logarithmic in time. Although, it may still be more accurate to say that for an unbalanced tree, the runtime is in the worst case linear.

<blockquote class="note">
  <strong>LOGARITHM</strong> 
  <p>
    Logarithm is the inverse of exponents. 2<sup>3</sup> is the equivalent of 2 * 2 * 2, which is 8. Now log<sub>2</sub>8 is the inverse of 2<sup>3</sup>. It means: "how many times do you have to multiply 2 by itself to get a result of 8?". Since you have to multiply 2 by itself 3 times to get 8, log<sub>2</sub> 8 = 3. Another way to view this is: How many times do we need to divide 8 by 2 until we end up with 1?
  </p>
</blockquote>

### Superlinear O(n*log(n))  

An algorithm is said to run in **n log n** time if the execution time of an algorithm is proportional to
the product of input size and logarithm of the input size.

Examples:

1. Merge-Sort
2. Quick-Sort (Average case)
3. Heap-Sort

Most of the sorting operate in (n log n) time. This includes popular sorting algorithms like quicksort, mergesort or heapsort. Actually, quicksort has O(n<sup>2</sup>) time in worst-case complexity and O(n log n) as the average case complexity.

### Quadratic O(n<sup>2</sup>)

An algorithm is said to run in logarithmic time if the execution time of an algorithm is proportional to
the square of the input size. Examples:

1. Bubble-Sort
2. Selection-Sort
3. Insertion-Sort

### Cubic O(n<sup>3</sup>)  

Brute force algorithms often run in O(n<sup>2</sup>) or O(n<sup>3</sup>) time where you may be looping within a loop. It's easy to identify if you see a for-loop inside a for-loop, where for each element i you iterate through another element j, for instance. 

A common scenario is, given two arrays, find the common elements in each array where you would simply go through each element and check whether it exists in the other array. This would execute in O(n*m) time, where n and m are the sizes of each array. It's still great to name these brute force algorithms if you can identify them.

### Exponential O(2<sup>n</sup>)

Exponential algorithms are quite terrible in running time. A classic example is determining every permutation of a set of n bits (it would take 2n combinations). Another example is computing the fibonacci sequence: 

```
fib(n) = fib(n-1) + fib(n-2)
```

where for each item, it requires the computation of two more subproblems.  

![Complexity Functions](/assets/images/complexity-functions.png)

### Deriving the Runtime Function of an Algorithm

#### Constants

Each statement takes a constant time to run. Time Complexity is O(1).

#### Loops

The running time of a loop is a product of running time of the statement inside a loop and number of iterations in the loop. Time Complexity is O(n).

#### Nested Loop

The running time of a nested loop is a product of running time of the statements inside loop multiplied by a product of the size of all the loops. Time Complexity is O(n<sup>c</sup>).

Where c is a number of loops. For two loops, it will be O(n<sup>2</sup>).

#### Consecutive Statements

Just add the running times of all the consecutive statements.

#### if-else Statement

Consider the running time of the larger of if block or else block. Ignore the other one.

#### Logarithmic Statement

If each iteration is decreasing the input size by a constant factors. Time Complexity = O(log n).

### Factorial O(n!)  

These algorithms are the slowest and don't show up that often. You might see this in combinatorial problems or the traveling salesman problem, where given n nodes, you need to find the optimal path from start to finish. 

In your first iteration, you have a selection of n cities to visit, then n-1 cities, then n-2 cities, n-3 cities, etc., until you reach the last city. That runtime is:

```
n * (n - 1) * (n - 2) * (n - 3) ... 1 = O(n!)
```

![Complexity Classes](/assets/images/complexity-classes.png)

![Complexity Classes](/assets/images/complexity-classes.png)

## Some Tips

Do not overcomplicate this like saying "This is O(3 * k *  n<sup>2</sup>), where k is the number of comparisons." Most people don't care about this level of detail, and you can often get away with simply saying: "This is quadratic time because we have two for-loops, each one iterating from 1 to n."

One more tip - do not say "This is O(m + v + e)," when you haven't defined what m, v, or e are. You generally want to say "... where m is the height of the matrix, v is the number of vertices, e is the number of edges, etc.," Once you start reciting formulas without defining the constants you're using, your analysis will appear amateurish.

Most interviewers will focus on time-complexity, but it is great to also consider space-complexity too. Algorithms are commonly tradeoffs between time and space. For instance, you may be able to take a polynomial algorithm and convert it to an O(n) algorithm, but it requires the creation of a hashmap of size O(n). That's a good trade-off to be able to talk about because additional space is needed.

<blockquote class="note">
  <strong>BEST CASE AND AVERAGE CASE</strong> 
  <p>
    You usually don't need to know omega and theta, though they're not that difficult. It's just the best case and average case.
  </p>
</blockquote>

When assessing time vs space complexity, it would be generally better to focus on reducing time complexity at the expense of space complexity. The tradeoffs for the example of the polynomial algorithm in reducing the time complexity to O(n) at the expense of a hashmap of size O(n). Space complexity would impact mostly usage of resources (memory) but as long as it doesn't blow up, optimizing the time efficiency comes first.

You generally want to optimize for time. Do not assume that time efficiency is the optimal solution without explaining the trade-offs in space. A good candidate will have mastery of time-space analysis and always be talking that through.

Big O is by definition for worst-case. The exception is for trees. It may help to assume that the trees are balanced though (usually giving O(logn) complexity) or for hashmaps to assume no collisions.

However, you can make a few assumptions usually like hashmaps will have no collisions, that trees are properly balanced, or that numbers are properly random. It's good to give a complete analysis and say something like "on average you'll get O(log n) though in the worst case this could be as bad as O(n) if the tree is not balanced." 

## Basic Data Structures

The basic data structures to learn how to perform Big-O analysis:

**Array, Matrix, Linked List (double, single, circular)**

- Representation
- Traversal
- Insert
- Find
- Delete
- Update
- Detect loop, find linked list circle start point

**Stack**

- Representation
- push
- pop
- peek
- full? / empty?

**Queue**

- Representation
- enqueue
- dequeue
- peek
- full? / empty?

**Tree (Binary Tree and Binary Search Tree)**

- search
- insert
- post-order, in-order, pre-order traversal

**Graph**

- Representation
- Implementation
- DFS/BFS
- Dijkstra's Algorithm

Feel free to add advanced data structures to this list for your level.

## Pros and Cons

Create a table for each data structure to compare them. What are the time-space complexities? It's very important to build a solid understanding of data structures and algorithms before tackling real coding interview questions.
