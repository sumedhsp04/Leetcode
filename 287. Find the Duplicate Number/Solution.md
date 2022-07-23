## [287. Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/)

## Description

Given an array of integers  `nums`  containing `n + 1`  integers where each integer is in the range  `[1, n]`  inclusive.

There is only  **one repeated number**  in  `nums`, return  _this repeated number_.

You must solve the problem  **without**  modifying the array  `nums` and uses only constant extra space.

**Example 1:**

**Input:** nums = [1,3,4,2,2]
**Output:** 2

**Example 2:**

**Input:** nums = [3,1,3,4,2]
**Output:** 3

**Constraints:**

-   `1 <= n <= 105`
-   `nums.length == n + 1`
-   `1 <= nums[i] <= n`
-   All the integers in  `nums`  appear only  **once**  except for  **precisely one integer**  which appears  **two or more**  times.

**Follow up:**

-   How can we prove that at least one duplicate number must exist in  `nums`?
-   Can you solve the problem in linear runtime complexity?

## Solutions

<!-- tabs:start -->

### **Python3**

### **Method1**

```python
class Solution:
    def findDuplicate(self, nums: List[int]) -> int:
       
        for i in range (len(nums)):
            for j in range (i+1,len(nums)):
                if nums[i] == nums [j]:
                    return nums[i]
```
### **Method2**
```python
class Solution:
    def findDuplicate(self, nums: List[int]) -> int:
        nums.sort()
        prv = None
        for curr in nums:
            if curr == prv:
                return curr
            prv = curr
```
