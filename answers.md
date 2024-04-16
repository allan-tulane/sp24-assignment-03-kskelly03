# CMPS 2200 Assignment 3
## Answers

**Name:** Kevin Skelly


Place all written answers from `assignment-03.md` here for easier grading.
1. A) Always choose the largest possible k such that $2^k$ is less than or equal to $N$. Subtract this amount from $N$ and repeat until $N = 0$.

   B) Let $(a_0, a_1, ... , a_k)$ denote an optimal solution, where $a_i$ indicates the number of coins of denomination $2^i$. It should be noted that we must have $a_i < 2$ for every single $i \leq k$. This is because if we had some $a_i \geq 2$, then we could take two of those coins and turn them into a single $a_{i+1}$ coin. This has the same value and 1 less coin as the former option, so the original solution was not optimal. This is the property that the remaining proof rests on.
  The configuration denoted by the previously stated property is the exact same as the greedy solution from A). This is because to get a total value of N, you would first pick $a_k = ⌊ N / (2^k) ⌋$, where $2^k <= N$. If $N \geq 0$ after this first choice, for $i < k$, $a_i = ⌊(Nmod2 ^{i+1})*2^{-i}⌋$. This is the only solution that satisfies the property that there aren't two of any denomination of coin. The coin amounts are a base 2 representation of $Nmod2^k$.

   C) $W(n) = O(logn)$, $S(n) = O(logn)$
3. A) For one simple counterexample, assume Fortuito has denominations [10, 6, 1]. If you go to Fortuito and need change for 12, the greedy algorithm designates that you receive 3 coins: 10, 1, and 1. However, the optimal solution in this case would be to ignore the largest value and take 2 coins of value 6.

   B) The optimal substructure property means that the optimal solution to a given problem can be divided into the optimal solution to sub-problems of the original problem. Consider any optimal solution for making $N$ cents using denominations $[D_0, D_1, ..., D_k]$. Now consider breaking that optimal solution into two halves such that the left half amounts to x cents and the right half amounts to N-x.

      The optimal substructure property claims that the left half is the optimal way to make change for x cents using the given denominations. The same goes for the right half. We can prove this by assuming the contradiction that there is a better way to compile x cents. However, if this were true then the left half could be replaced with this new better combination. This would violate the optimal solution agreed on in the assumptions and is thus a contradiction. The same goes for the right half.

   C) d is an array of denomination values, n is the amount of change to be made
```python
change[d, n]:
   k = len(d)
   optimal[0] = 0
   for i in range (1, n):
      min = inf
      for j in range (1,k):
         if d[i] <= i:
            if (1+optimal[i-d[j]) < min:
               min = 1+optimal[i-d[j]
               coin = j
      optimal[i] = min
return optimal
``` 
    
