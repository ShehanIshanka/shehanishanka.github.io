```python 
class Solution:
    def getRow(self, rowIndex: int) -> List[int]:
        if rowIndex == 0:
            return [1]
        
        output = [1, 1] 

        for j in range(1, rowIndex):
            l = len(output)

            if l % 2 == 0:
                mid  = int(l/2)
                output.insert(mid, output[mid]*2)
            else:
                mid  = l//2
                val = output[mid] + output[mid-1]
                output[mid] = val
                output.insert(mid+1, val)
            
            l = l + 1

            for i in range(mid-1, 0, -1):
                output[i] = output[i] + output[i-1]
                output[l - i - 1] = output[i]

        return output
```

- Time Complexity - O(n<sup>2</sup>)
- Space Complexity - O(n)