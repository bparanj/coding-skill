## Longest Palindromic Substring

This question is Amazon's top 100 questions asked during the interview. Given a string s, find the longest palindromic substring in s. Example:

```
Input: 'babad'
Output 'bab' or 'aba'
```

I had to make corrections to the code in my videos on how to solve this problem. The fixes are:

1. To exclude the last character, you have to use n-2 because the s[0] == s[n-1] checks the first and last character.
2. Going from first character to and less than the last character requires s[0..n-2]. It's not s[0..n-1].

```ruby
def palindrome?(s)
  n = s.length
  if n <= 1
    return true
  else 
    return (s[0] == s[n-1]) && palindrome?(s[1..n-2])
  end
end

def longest_palindrome(s)
  n = s.length
  if palindrome?(s)
    return s
  else
    saux1 = longest_palindrome(s[1..n-1])
    saux2 = longest_palindrome(s[0..n-2])
    if saux1.length > saux2.length
      return saux1
    else
      return saux2
    end
  end
end

p longest_palindrome("babad")
```

Next step is to make this solution optimal by using dynamic programming.

