---
layout: post
title: Traversing Two Trees in Parallel
---

Given two trees, determine whether they are copies of one another. This is a common coding interview question.

### Clarification Questions

It is intentionally vague. Sometimes, interviewers will ask question to see if you can define the problem scope by asking the necessary clarifying questions. 

- What are the data structures?  
- What’s the function signature?  
- Are there classes?  
- What does the tree look like, how many children are there?  

### Variations

It is up to you how you would design it. So, this is about traversing two trees in parallel. There are variations of this question like:

- Are two trees copies of each other?
- Is there a node in one tree that is considered the same as a node in another tree?

### Solution

You might be familiar with traversing a single tree. But when asked to traverse two trees at the same time, it tests if you understand the algorithm. There is nothing tricky about this questions. We will see the code with two variations.

First, think about how you represent children. Sometimes it is simpler to represent them as an array, rather than as a `left` node and a `right` node.  Sometimes, a tree can have multiple fan-outs, so the array representation is more flexible. It depends on the problem at hand.

The second thing is the implementation is in recursive form and then in iterative form. You will find that the recursive form is a bit simpler. The iterative form requires passing a lot of state around, and nearly warrants creating a new data structure just to encapsulate the state of two nodes. I get away with it using a `stack of arrays` for brevity.

This solution uses object-oriented style. So instead of having a function `isClone(a, b)`, I’m going to use the form `a.isClone(b)`. Just be aware that there are multiple ways of doing these method params.

```python
class Node:
  def __init__(self, value=None, children=[]):
    self.value = value
    self.children = children

  def prettyPrint(self):
    print self.value
    for child in self.children:
      child.prettyPrint()

  def isClone(self, n2):
    if self.value != n2.value:
      return False
    if len(self.children) != len(n2.children):
      return False
    for i in range(0, len(self.children)):
      if not self.children[i].isClone(n2.children[i]):
        return False
    return True

  def isCloneIterative(self, n2):
    stack = [ (self, n2) ]
    while len(stack):
      (c1, c2) = stack.pop()
      if c1.value != c2.value:
        return False
      if len(c1.children) != len(c2.children):
        return False
      for i in range(0, len(c1.children)):
        stack.append( (c1.children[i], c2.children[i]) )
    return True

  #     1
  #    / \
  #   2   3
  #  / \
  # 4   5

n = Node(1)
n.children = [Node(2), Node(3)]
n.children[0].children = [Node(4), Node(5)]

n2 = Node(1)
n2.children = [Node(2), Node(3)]
n2.children[0].children = [Node(4), Node(5)]

print n.isClone(n2)
print n.isCloneIterative(n2)
```
