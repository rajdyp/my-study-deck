## Find the maximum and minimum element in an array

```python
# O(n log n)
arr = [5, 2, 9, 1, 5, 6]
arr.sort()
print(arr[-1])
print(arr[0])
```

```python
# O(n)
def find_min_max(arr):
    if len(arr) == 0:    # edge case
        return None, None 
    
    max_element = arr[0]    # 7
    min_element = arr[0]    # 7

    for num in arr:
        if num > max_element:    # 7 --> 9
            max_element = num
        if num < min_element:    # 7 --> 5 --> 2 --> 1
            min_element = num

    return max_element, min_element

arr = [5, 2, 9, 1, 5, 6]
max_num, min_num = find_min_max(arr)
print(max_num)
print(min_num)
```
