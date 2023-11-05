## Two sum

```python
# O(n)
def two_sum(nums, target):
    mydict = {}
    for i, n in enumerate(nums):
        diff = target - n
        if diff in mydict:
            return [mydict[diff], i]
        mydict[n] = i
    return []
    
nums = [2,15,11,7]
target = 9
print(two_sum(nums, target))
```
