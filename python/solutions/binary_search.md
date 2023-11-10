## Binary search

```python
# linear search
# O(n)
def search(nums, target):
    for i in range(len(nums)):
        if nums[i] == target:
            return i
    return -1

n1 = [-1,0,3,5,9,12]
t1 = 9
print(search(n1, t1))

n2 = [-1,0,3,5,9,12]
t2 = 2
print(search(n2, t2))
```

```python
# O(log n)
def search(nums, target):
    left, right = 0, len(nums) - 1
    while left <= right:
        mid = (left + right) // 2
        if nums[mid] == target:
            return mid
        elif nums[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1

n1 = [-1,0,3,5,9,12]
t1 = 9
print(search(n1, t1))

n2 = [-1,0,3,5,9,12]
t2 = 2
print(search(n2, t2))
```
