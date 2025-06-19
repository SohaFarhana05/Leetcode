## Day - 02  (17-06-2025)

Today is the second day of me documenting leetcode daily!!

## 3405. Count the Number of Arrays with K Matching Adjacent Elements
### Description - You are given three integers n, m, k. A good array arr of size n is defined as follows: Each element in arr is in the inclusive range [1, m]. Exactly k indices i (where 1 <= i < n) satisfy the condition arr[i - 1] == arr[i]. Return the number of good arrays that can be formed. Since the answer may be very large, return it modulo 109 + 7.


Okayyyy, so what we have today is leetcode hard and I also find it pretty hard but I have learnt on how to solve this. What is better skipping or learning what you don't know?? LEARNING right??? 
So I have spent some time to learn how to solve this and actually it breaks it in a little understandable manner.


### Approach - 01 ( Brute Force )

So here we just are counting all the ways on how this problem can be solved.

``` Python 
class Solution:
    def countGoodArrays(self, n: int, m: int, k: int) -> int:
        r = n-k
        first = math.comb(n-1,k)
        second = m *( (m-1)**(r-1))
        return (first* second) % 1000000007

```

Time Complexity - O(N + log MOD) \
Space Complexity - O(N)
### Approach - 02 ( Optimal Solution )

``` Python


```
Time Complexity - O() \
Space Complexity - O()