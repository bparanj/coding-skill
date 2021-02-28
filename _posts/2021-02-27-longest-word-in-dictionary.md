---
layout: post
title: Longest Word in Dictionary
excerpt: Checking prefixes to construct the longest word in Dictionary
---
 

## Solution

I modified the solution that I found online to make it easier to follow the tracing of calls in a debugger. The code is concise and elegant.


```ruby
require 'set'

def longest_word(words)
  output = ''
  
  # Sort alphabetically
  words = words.sort
    
  set = Set.new
    
  words.each do |word|
    prefix = word[0, word.size-1]
    found = set.include?(prefix)

    if word.size == 1 || found
      # Pick only bigger words to update the result
      if word.size > output.size
        output = word
      end
      # remember the words we have seen so far
      set.add(word)
    end
  end
  
  return output
end

words = ["yo","ew","fc","zrc","yodn","fcm","qm","qmo","fcmz","z","ewq","yod","ewqz","y"]

p longest_word(words)

```

Run this through the debugger to understand how to code works.

