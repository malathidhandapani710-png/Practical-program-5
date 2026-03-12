class Solution:
    def findTwoElement(self, arr):
        n = len(arr)
        repeating = -1
        missing = -1
        
        # Step 1: Find the repeating number
        for i in range(n):
            val = abs(arr[i])
            # Use val-1 as the index
            if arr[val - 1] < 0:
                repeating = val
            else:
                arr[val - 1] = -arr[val - 1]
        
        # Step 2: Find the missing number
        for i in range(n):
            # If the value is still positive, then (i + 1) is the missing number
            if arr[i] > 0:
                missing = i + 1
                break
                
        return [repeating, missing]
