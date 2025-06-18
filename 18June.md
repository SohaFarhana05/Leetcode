## Day - 03  (18-06-2025)

Today is the third day of me documenting leetcode daily!!

##  2966. Divide Array Into Arrays With Max Difference
### Description - You are given an integer array nums of size n where n is a multiple of 3 and a positive integer k.
Divide the array nums into n / 3 arrays of size 3 satisfying the following condition:
The difference between any two elements in one array is less than or equal to k.
Return a 2D array containing the arrays. If it is impossible to satisfy the conditions, return an empty array. And if there are multiple answers, return any of them.

 


### Approach - 01 ( Brute Force )

So here we just sorting the array and dividing it into chunks of size 3 and checking whether what we obtain is according to the condition or not i.e max - min in an array of size of should be less than or equal to k, and then checking whether the size of both arrays are matching or not, if yes then we can go and return the array else we have to return an empty array.
Brute force is pretty nice and easy to code here.

``` Python 
class Solution:
    def divideArray(self, nums: List[int], k: int) -> List[List[int]]:
        ans = []
        nums = sorted(nums)
        c = 0
        l = []
        # print(nums)
        for i in range(len(nums)):
            if c==0 or c==1 or c==2:
                l.append(nums[i])
                c+=1
            elif c==3:
                ans.append(l)
                l = []
                l.append(nums[i])
                c = 1
        ans.append(l)
        a = []
        c = 0
        n = len(nums)//3
        for i in range(len(ans)):
            if ans[i][2]-ans[i][0]<=k: 
                a.append(ans[i])
                c+=1
        # print(a)
        # print(c , n)
        if c==n:
            return a   
        return []        

```

Time Complexity - O(NLogN) \
Space Complexity - O(N)
### Approach - 02 ( Optimal Solution )
Here also we are almost using the same logic that we kinda used in brute force but here we are ensuring not to use another array to store instead return an empty array directly if the difference exceeds k because that is exactly what the question wanted right. Now I am sleepy today after returning from my internship and am stopping here but I will try to optimize this more in future!!
Good luck you reading this! 
``` Python
class Solution:
    def divideArray(self, nums: List[int], k: int) -> List[List[int]]:
        ans = []
        nums = sorted(nums)
        for i in range(2,len(nums),3):
            if nums[i]-nums[i-2]>k:
                return []
            else:
                ans.append([nums[i-2],nums[i-1],nums[i]])
        return ans
        
```
Time Complexity - O(N) \
Space Complexity - O(1)