# leetcode_Two_Sum
+ target 값이 주어지고 array input값이 주어지면 그 target을 구할 수 있는 두 숫자의 위치를 출력
----
### Example 1
```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```
### Example 2
```
Input: nums = [3,2,4], target = 6
Output: [1,2]
```
### Example 3
```
Input: nums = [3,3], target = 6
Output: [0,1]
```
----
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        n = len(nums) # input의 길이
        dict = {} # 저장 함수
        
        for i in range (n):
            val = target - nums[i] # 값을 빼서 그 값이 어디 있는지 계산
            if(val in dict): # 만약 값이 저장 함수 dict에 들어있고
                if i > dict[val]: # i의 위치가 내가 찾은 나머지 뺀 값의 위치보다 크면
                    return [dict[val], i] # 위치 바꿔서 출력
                else:
                    return [i, dict[val]] # 아니면 그냥 출력
            else:
                dict[nums[i]] = i # 만약 저장 함수 dict에 없을때 , 그 숫자에 i index값을 저장
```
----
## Result
Runtime: 119 ms, faster than 43.55% of Python3 online submissions for Two Sum.\
Memory Usage: 15.2 MB, less than 49.72% of Python3 online submissions for Two Sum.
