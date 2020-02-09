---
layout: post
title: Four Criteria for Technical Interview Evaluation
---

Let's discuss how your performance is evaluated in the interview process. There are four criteria that will determine whether you get an offer or not. Once you know what they are, you can work on improving them. Even if you pass the coding interview, you may not pass the hiring committee. Because you might have failed on one of the criteria that is not related to coding. You need to score well on all criteria to proceed further. 

## Coding

This is your coding ability. It is about the syntax, how the code looks, whether you can write it quickly and elegantly etc.

- Can you write the code that you said you would write?  
- Are your variables and functions well-named? 
- How clean and structured is your code?  
- Did you cover the edge and base cases?  

We discuss this aspect in more detail in the article on [Interview Performance Evaluation Criteria : Coding]({% post_url 2019-09-05-interview-performance-evaluation-criteria-coding %})

## Data Structures and Algorithms

You must demonstrate your mastery of data structures and algorithms. This may involve creating data structures or showing you know Object-Oriented Programming.

- Can you come up with a suitable algorithm or data structure to solve the problem efficiently?  
- Can you analyze that solution in terms of time & space complexity and the trade-offs?  
- Did you demonstrate mastery of the data structures available and create your own data structures as necessary with private/public APIs?  
- Could you think critically to analyze various alternatives and compare brute force solutions versus more optimal solutions?

We discuss this aspect in more detail in the article on [Interview Performance Evaluation Criteria : Data Structures and Algorithms]({% post_url  2019-08-29-interview-performance-evaluation-criteria-ds-alg %})

## Design

Design separates the pros from the amateurs. Design shows your analysis skills such as time-space analysis and alternative approaches. You must show your ability to analyze a solution, regardless of whether you get the solution right or not.

Simply passing the white-boarding question does not mean that you did well. You should talk aloud so that you can explain the trade-offs that you are making.

Try to propose a few different designs and discuss the trade-offs in terms of time and space requirements. If you can indicate the Big O complexity before even coding, that would be ideal.

You will also shine if you are able to tackle ambiguity. Many questions are intentionally ambiguous. Clarify the question and problem-space quickly without wasting too much time so that you can move forward.

Devote sufficient time to discuss design but don't spend too much time. Leave yourself sufficient time to solve the problem. Speed is key.

## Communication

The ability to communicate clearly and effectively is crucial because coding is a team sport.

Many candidates as they are coding will say things like "uhmm... hold on... ah.... wait.... give me 2 seconds... oh... nevermind...". The words come out as a jumble of stuttered words. Some candidates talk in a too technical and incomprehensible way: "then we increment the variable i by the variable j minus one and check if j is equal to k."

This has to do with clarity. You must be able to explain a technical challenge clearly and concisely. It must inspire  and grasp the attention of the interviewer. This involves explaining the challenge, explaining what you did personally, and the result. 
 
It really helps if you can spend time to prepare a few stories beforehand and steer conversations towards those stories. You don't necessarily need to answer the interviewer's questions directly, if you can gently steer the conversation towards something more interesting.

Gauge the interviewer's reactions to ensure they are not getting bored. Show that you can accept feedback and collaborate and remember that your first and last impressions count. Be careful not to spend too much time with pointless stories. You are spending your own coding time, if you decide to ramble about something that does not provide value.

Above all, don't lose the interviewer. If you're rambling about technical jargon and the interviewer isn't responding, cut your story short. If you don't, the interviewer can become disinterested in you.  
The interviewers want to know what you personally did, not what your team did. Emphasize your own role here, concisely and clearly.

### STAR Format

Follow the STAR format and keep your stories concise and around 5 minutes. The key is transitioning to the story eloquently from the conversation with the interviewer and gauging their level of interest and cutting it short.

#### Situation

Explain the problem being faced by the team or project.

#### Task

Your responsibilities and assignments for the situation.

#### Action 

The set of steps you took to rectify or resolve the situation.

#### Result  

The end result of your actions.

## Speed and Efficiency 

Interviewers ask questions that can build on top of itself such as increasingly adding restrictions or pushing for faster time/space, so that interviewers can get some signal on the candidate's ability beyond just pass or fail.  

This is why fluidity and confidence is essential. So, even if you have heard these problems before, it helps to become good at these and see how the pros solve these problems. This helps you to recognize patterns in code and crafting elegant and simple solutions.

Study about time-space complexity. This is Big O (worst-case) analysis. N is the size of the input, like the size of an array or length of a string.

#### Constant Time O(1)

Very few programs are O(1) time.

#### Linear Time O(n)

Most optimal algorithms will be in a linear pass, or even a few linear passes O(k*n).  

#### Quadratic Time O(n^2) 

Most brute-force solutions will require O(n^2) time or slower, like checking if you have everything on your shopping list.

#### Logarithmic Time O(log(n))

This is very common for tree traversals like binary search.

#### Quasilinear Time O(n * log(n))

This is very common for sorting algorithms.

#### Exponential Time O(10^n) 

Common for brute-force like testing every numerical password combination.

#### Think about Time vs Space

Let's imagine you need to find all duplicate items in an array. You can solve that using a Hashmap in a single pass.  Or, you can simply sort the array and then look through it for similar elements next to each other. They're both valid solutions, and they're both just as good. The first version uses more space but less time O(n). The second version uses less space (almost zero space) but O(n*log(n)) time.  

It will boost your rating if you can point out the trade-offs between time and space. These two are always being traded off. You will almost always want to go for faster time, since space/memory is cheap. But highlighting this fact will help demonstrate the trade off.

Many candidates will solve the problem brilliantly, yet with no explanation of trade-offs. They will fail the interview. There are often problems where there is no definite solution. Rather, there are multiple competing solutions, none of them is perfect.

Often, there is no right answer. So, show that you understand this fact and that you can analyze and determine the trade-offs. It's not so much about the solution, it's about how you reach the solution.

Being able to do a quick analysis of time-space complexity before you even begin coding will win you big points. Most candidates can't visualize the algorithm and time-space complexity before-hand. But if you happen to come across a simple problem and know it, let them know earlier.

Just don't go over board and over-analyze. Some candidates will spend 10 minutes in analysis-paralysis. When the interviewer seems in agreement, start writing the code.

## Action Items

- If you've taken interviews in the past, reflect on them and think about these four criteria. Did you demonstrate all the four core criteria, with the fifth efficiency component?
- Think about how you can demonstrate each criteria in an interview.  
- Given a rating scale of 1-5, what do you think a 5 looks like for each criteria?  
- What does clean code mean to you?  
- Look over the Google Style Guides to understand style guidelines.  
- Pick your favorite language and check if your coding standards match that of Google's official guides.  

## Conclusion

It's not whether you reach the solution, but how you reach that solution that is important. Your technique and approach to the coding problem matters the most in evaluation of your coding interview performance. During practice, if you can hit all the criteria, you'll be well prepared.
