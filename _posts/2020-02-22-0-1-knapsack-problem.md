---
layout: post
title: 0-1 Knapsack Problem
excerpt: How is naive recursive solution time complexity is O(2<sup>n</sup> ) in 0-1 Knapsack problem?
---

## Naive Approach

A simple solution is to consider all subsets of items and calculate the total weight and value of all subsets. Consider the only subsets whose total weight is smaller than W. From all such subsets, pick the maximum value subset.


## Optimal Sub-structure

To consider all subsets of items, there can be two cases for every item.

1. Case 1: The item is included in the optimal subset.
2. Case 2: The item is not included in the optimal set.

Therefore, the maximum value that can be obtained from 'n' items is the max of the following two values.

1. Maximum value obtained by n-1 items and W weight (excluding n <sup>th</sup> item).
2. Value of nth item plus maximum value obtained by n-1 items and W minus the weight of the nth item (including nth item).

If the weight of 'nth' item is greater than 'W', then the nth item cannot be included and Case 1 is the only possibility.

## Implementation

```java
/* A Naive recursive implementation  
of 0-1 Knapsack problem */
class Knapsack { 
  
    // A utility function that returns 
    // maximum of two integers 
    static int max(int a, int b) 
    { 
        return (a > b) ? a : b; 
    } 
  
    // Returns the maximum value that 
    // can be put in a knapsack of 
    // capacity W 
    static int knapSack( 
        int W, int wt[], 
        int val[], int n) 
    { 
        // Base Case 
        if (n == 0 || W == 0) 
            return 0; 
  
        // If weight of the nth item is 
        // more than Knapsack capacity W, 
        // then this item cannot be included 
        // in the optimal solution 
        if (wt[n - 1] > W) 
            return knapSack(W, wt, val, n - 1); 
  
        // Return the maximum of two cases: 
        // (1) nth item included 
        // (2) not included 
        else
            return max( 
                val[n - 1] + knapSack(W - wt[n - 1], 
                                      wt, val, n - 1), 
                knapSack(W, wt, val, n - 1)); 
    } 
  
    // Driver program to test 
    // above function 
    public static void main(String args[]) 
    { 
        int val[] = new int[] { 60, 100, 120 }; 
        int wt[] = new int[] { 10, 20, 30 }; 
        int W = 50; 
        int n = val.length; 
        System.out.println(knapSack(W, wt, val, n)); 
    } 
} 
```

**OUTPUT**

```
220
```

It should be noted that the above function computes the same sub-problems again and again. See the following recursion tree, K(1, 1) is being evaluated twice. The time complexity of this naive recursive solution is exponential (<sup>n</sup>).


```
In the following recursion tree, K() refers to knapSack().
The two parameters indicated in the following recursion tree are n and W. 

The recursion tree is for following sample inputs.

wt[] = {1, 1, 1}, W = 2, val[] = {10, 20, 30}
                       K(n, W)
                       K(3, 2)  
                   /            \ 
                 /                \               
            K(2, 2)                  K(2, 1)
          /       \                  /    \ 
        /           \              /        \
       K(1, 2)      K(1, 1)        K(1, 1)     K(1, 0)
       /  \         /   \          /   \
     /      \     /       \      /       \
K(0, 2)  K(0, 1)  K(0, 1)  K(0, 0)  K(0, 1)   K(0, 0)

Recursion tree for Knapsack capacity 2 units and 3 items of 1 unit weight.
```

## Complexity Analysis

Time Complexity: O(2<sup>n</sup>).
As there are redundant subproblems.

Auxiliary Space :O(1).
As no extra data structure has been used for storing values.
