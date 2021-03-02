---
layout: post
title: Permutation in String
excerpt: Code for Permutation in String and Find All Anagrams in a String problems.
---
 

## Solution

Comments explaining the code that I found online.

```ruby
def check_inclusion(s1, s2)
  goal = Array.new(26, 0)
  current = Array.new(26, 0)
    
  s1.chars.each do |c|
    goal[c.ord - 'a'.ord] += 1 
  end
    
  for i in (0...s2.size)
    current[s2[i].ord - 'a'.ord] += 1  
     
    # If the window size exceeds the size of s1
    # we need drop the character leaving the window
    if i >= s1.size
      current_index = s2[i - s1.size]
      current[current_index.ord - 'a'.ord] -= 1
    end
      
    if goal == current
      return true
    end
  end
    
  return false
end

```

With a few modifications, we can make the code work to solve Find All Anagrams in a String problem:

```ruby
def find_anagrams(s2, s1)
  output = []
  goal = Array.new(26, 0)
  current = Array.new(26, 0)
    
  s1.chars.each do |c|
    goal[c.ord - 'a'.ord] += 1 
  end
    
  for i in (0...s2.size)
    current[s2[i].ord - 'a'.ord] += 1  
     
    #  If the window size exceeds the size of s1
    #  we need drop of the character leaving the window
    if i >= s1.size
      current_index = s2[i - s1.size]
      current[current_index.ord - 'a'.ord] -= 1
    end
      
    if goal == current
      output << (i - s1.size + 1)
    end
  end
    
  return output 
end
```



