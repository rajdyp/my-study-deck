## Reverse an array

```python
# O(n)
a = [1, 2, 3, 4, 5]
a.reverse()
print(arr)
```

```python
# O(n)
def reverse_array(a):
    left, right = 0, len(a) -1    # left = 0, right = 4

    while left < right:
        # assignment operators assign RH side values to the operand that is present on the LH side
        a[left], a[right] = a[right], a[left]
        left += 1
        right -= 1

a = [1, 2, 3, 4, 5]
reverse_array(a)
print(a)

# explanation
# a[left]    --> a[0] = 5
# a[left]    --> a[1] = 4
# loop ends  --> a[2] = 3
# a[right]   --> a[3] = 2
# a[right]   --> a[4] = 1
```
