## Contains duplicate

```python
# O(n)
def containsDuplicate(nums):
        myset = set()
        for n in nums:
            if n in myset:
                return True
            myset.add(n)
        return False
    
nums = [1,2,3,1]
print(containsDuplicate(nums))

nums = [1,2,3,4]
print(containsDuplicate(nums))

nums = [1,1,1,3,3,4,3,2,4,2]
print(containsDuplicate(nums))
```
