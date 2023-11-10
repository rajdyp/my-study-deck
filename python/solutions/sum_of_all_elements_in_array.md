## Find the sum of all elements in an array
```python
# O(n)
a = [1, 2, 3, 4, 5]
sum = 0
for n in a:
    sum += n
print(sum)
```

```python
# O(n)
def find_sum_of_elements(a):
    sum = 0
    for n in a:
        sum += n
    return sum

a = [1, 2, 3, 4, 5]
print(find_sum_of_elements(a))
```
