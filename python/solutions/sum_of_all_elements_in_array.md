## Find the sum of all elements in an array
```python
# O(n)
arr = [1, 2, 3, 4, 5]
sum = 0
for n in arr:
    sum += n
print(sum)
```

```python
# O(n)
def find_sum_of_elements(arr):
    sum = 0
    for e in arr:
        sum += e
    return sum

arr = [1, 2, 3, 4, 5]
print(find_sum_of_elements(arr))
```
