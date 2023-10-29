## Reverse an array

```python
# O(n)
arr = [1, 2, 3, 4, 5]
arr.reverse()
print(arr)
```

```python
# O(n)
def reverse_array(arr):
    left, right = 0, len(arr) -1    # left = 0, right = 4

    while left < right:
        # assignment operators assign RH side values to the operand that is present on the LH side
        arr[left], arr[right] = arr[right], arr[left]
        left += 1
        right -= 1

arr = [1, 2, 3, 4, 5]
reverse_array(arr)
print(arr)

# explanation
# arr[left]  --> arr[0] = 5
# arr[left]  --> arr[1] = 4
# loop ends  --> arr[2] = 3
# arr[right] --> arr[3] = 2
# arr[right] --> arr[4] = 1
```
