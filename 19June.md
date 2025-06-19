## Day - 04  (19-06-2025)

I guess we are getting along well now and have manages to code a question daily and document it but what really matters is whether we are solving or not!!

## 2294. Partition Array Such That Maximum Difference is K
### Description - You are given an integer array nums and an integer k. You may partition nums into one or more subsequences such that each element in nums appears in exactly one of the subsequences.

Return the minimum number of subsequences needed such that the difference between the maximum and minimum values in each subsequence is at most k.

A subsequence is a sequence that can be derived from another sequence by deleting some or no elements without changing the order of the remaining elements.



### Approach - 01 ( Brute Force )

So, till now I have only got one approach so I will be explaining this only, in case I get any other thought I will commit it again!! So the logic here is we are sorting the array first and then maintaining an index element where we are storing the current minimum as in this question we have to only work with minimum and maximum. We now have current minimum of an array and we have to decide till where the difference is not excedding. So I compare the current minima with next array element, if it exceeds then we know that we will have to break it there else we can add elements in that array. Here c denoted how many arrays will we require. As here we are not told to print the arrays, this method correctly works as this perfectly specifies how many arrays will we have to break the given array into satisfying the condition given.

``` Python 
class Solution:
    def partitionArray(self, nums: List[int], k: int) -> int:
        c = 1
        nums = list(sorted(set(nums)))
        index = nums[0]
        for i in range(0,len(nums)):
            if (nums[i] - index)>k:
                c+=1
                index = nums[i]
        return c      

```

Time Complexity - O(NLogN) \
Space Complexity - O(N)
