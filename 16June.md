## Day - 01  (16-06-2025)

Today will mark the first day where I will be documenting what I will code for the LeetCode Daily!!
I love to code in Python and I choose it to document.

## 2016. Maximum Difference Between Increasing Elements
### Description - Given a 0-indexed integer array nums of size n, find the maximum difference between nums[i] and nums[j] (i.e., nums[j] - nums[i]), such that 0 <= i < j < n and nums[i] < nums[j].

Return the maximum difference. If no such i and j exists, return -1.

This question is ranked easy. 
Even I personally found the question easy too as brute force was just simple for loops and we can optimize it also in a very pretty easy manner.

### Approach - 01 ( Brute Force )

``` Python 
class Solution:
    def maximumDifference(self, nums: List[int]) -> int:
        diff = -1
        for i in range(0,len(nums)):
            for j in range(1,len(nums)):
                if i!=j and i<j and nums[i]<nums[j]:
                    diff = max(diff,abs(nums[i]-nums[j]))
        return diff
```

Here we keep track of each and every difference only if the next number is greater than the previous i.e i and then compare with the previous difference and update the difference if it is more than the previous tracked value. As we are iterating twice, the time complexity here becomes quadratic. We are looping through the array twice and just simply checking that i should not be equal to j and i should be less than j and of course the nums[i] should also be less than nums[j]. \
Time Complexity - O(N^2) \
Space Complexity - O(1)
### Approach - 02 ( Optimal Solution )

So here what I tried was to maintain the minimum element from the left as we have to maximize nums[j]-nums[i], the one best approach to do so is to maximize nums[j] as high as possible and minimize nums[i] as less as possible. So we are keeping track of minimum element possible till then and finding difference between the current element and minimum element we have tracked till now, this way we can obtain the answer in linear time.

``` Python
class Solution:
    def maximumDifference(self, nums: List[int]) -> int:
        diff = -1
        mini = float('inf')
        diff = -1
        for i in range(0,len(nums)):
            mini = min(mini,nums[i])
            diff = max(diff,nums[i]-mini)
        if diff==0:
            return -1
        return diff

```
Time Complexity - O(N) \
Space Complexity - O(1)