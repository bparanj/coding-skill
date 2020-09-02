---
layout: post
title: Flatten Binary Tree to Linked List in Place
excerpt: In order traversal and Post order traversal in action
---

Reading the explanation of the output was a bit scary. After looking at the hint, it was easy to code the solution because the condition to check was expressed directly in the code.

The input and output are:

```
 @param {Integer[]} candies
 @param {Integer} extra_candies
 @return {Boolean[]}
```

The base case is when the input is nil. This can happen when the input to the program is nil or when we reach the leaf node (it has no children, nothing to compute). We return without doing any computation.

## Greedy Approach

Solution:

```ruby
def kids_with_candies(candies, extra_candies)
    result = []
    max = candies.max
    
    candies.each do |candy|
       result << (candy + extra_candies >= max) 
    end
    result
end
```
