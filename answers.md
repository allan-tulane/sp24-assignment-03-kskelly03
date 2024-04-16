# CMPS 2200 Assignment 3
## Answers

**Name:**Kevin Skelly


Place all written answers from `assignment-03.md` here for easier grading.
1. A) Always choose the largest possible k such that 2^k is less than or equal to N. Subtract this amount from N and repeat until N = 0.
   B) Let (a_0, a_1, ... , a_k) denote an optimal solution, where a_i indicates the number of coins of denomination 2^i. It should be noted that we must have a_i < 2 for every single i <= k. This is because if we had some a_i >= 2, then we could take two of those coins and turn them into a single a_i+1 coin. This has the same value and 1 less coin as the former option, so the original solution was not optimal. This is the property that the remaining proof rests on.
  The configuration denoted by the previously stated property is the exact same as the greedy solution from A). This is because to get a total value of N, you would first pick a_k = ⌊ N / (2^k) ⌋, where 2^k <= N. If N != 0 after this first choice, for i < k a_i = ⌊(Nmod2 ^(i+1))c^−i⌋. This is the only solution that satisfies the property that there aren't two of any denomination of coin. The coin amounts are a base 2 representation of Nmod2^k.
      
    
