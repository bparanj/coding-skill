---
layout: post
title: Longest Palindromic Substring
excerpt: Recursion, Recursion with Memoization and DP solutions
---

The input and output are:

```
Input: String
output: String
```

The base case is when the input string is either 0 or 1 in length. We have to consider three cases, the entire string can be a palindrome, if so that is the longest palindrome. If not, either the string that excludes the first character or the string that excludes the last character can be a palindrome. One of this can be the longest when we make recursive calls. 

## Recursive Solution

It is easy to make mistakes in discarding the last character because we are used to using n-1 for the end of the string. To discard the last character we have to use n-2 for reducing the input size to the recursive call.

```ruby
def palindrome?(s)
  s == s.reverse
end

def longest_palindrome?(s)
  n = s.size
  
  if n <= 1
    return s
  else
    p n
    p s[1..n]
    p s[0..n-2]
  end
end

p longest_palindrome?('abbda')
```

This will work for small inputs but will result in Time Limit Exceeded error for large inputs. 
