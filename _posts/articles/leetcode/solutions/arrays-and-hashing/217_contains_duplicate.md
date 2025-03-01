```python 
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        counts = {}
        for num in nums:
            counts[num] = counts.get(num, 0) + 1
            if counts[num] > 1:
                return True
        return False
```

- Time Complexity - O(n)
- Space Complexity - O(n)