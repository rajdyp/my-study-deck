## Find the maximum and minimum element in an array

```python
# O(n log n)
a = [5, 2, 9, 1, 5, 6]
a.sort()
print(a[-1])
print(a[0])
```

```python
# O(n)
def find_min_max(a):
    if len(a) == 0:    # edge case
        return None, None 
    
    max_element = a[0]    # 7
    min_element = a[0]    # 7

    for num in a:
        if num > max_element:    # 7 --> 9
            max_element = num
        if num < min_element:    # 7 --> 5 --> 2 --> 1
            min_element = num

    return max_element, min_element

a = [5, 2, 9, 1, 5, 6]
max_num, min_num = find_min_max(a)
print(max_num)
print(min_num)
```
