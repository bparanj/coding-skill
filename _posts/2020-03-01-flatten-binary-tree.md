---
layout: post
title: Flatten Binary Tree to Linked List in Place
excerpt: In order traversal and Post order traversal in action
---

Definition for a binary tree node. 

```ruby
class TreeNode
  attr_accessor :val, :left, :right
  def initialize(val = 0, left = nil, right = nil)
    @val = val
    @left = left
    @right = right
  end
end
```

The input and output are:

```
@param {TreeNode} root
@return {Void} Do not return anything, modify root in-place instead.
```

The base case is when the input is nil. This can happen when the input to the program is nil or when we reach the leaf node (it has no children, nothing to compute). We return without doing any computation.

## Inorder Traversal

Solution:

```ruby
def flatten(node)
  if node.nil?
    return
  end
   
  if node.left
    flatten(node.left)
    right = node.right
    node.right = node.left
    node.left = nil
    current = node.right
    while current.right
      current = current.right 
    end
    current.right = right
  end

  if node.right
    flatten(node.right) 
  end
end
```

## Postorder Traversal
 
Solution:

```ruby
def flatten(node)
  if node.nil?
      return
  end
  
  flatten(node.left)
  flatten(node.right)
  
  if node.left
   temp = node.right
   node.right = node.left
   
   current = node.right
   while current.right
     current = current.right
   end
   current.right = temp
   node.left = nil
  end

end
```
