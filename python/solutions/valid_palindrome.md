## Valid palindrome

```yaml
# Extra memory

- Filter alphanumeric characters
- Compare "s" with reverse of "s"
```

```python
# O(n)
def is_palindrome(s):
    temp_s = ""
    for char in s:
        if char.isalnum():
            temp_s += char.lower()

    if temp_s == temp_s[::-1]:
        return True
    return False

s = "A man, a plan, a canal: Panama"
print(is_palindrome(s))

s = "race a car"
print(is_palindrome(s))

s = " "
print(is_palindrome(s))
```


```yaml
# Two pointer solution

- Take two pointers "left" and "right"
- If char is not alphanumeric than just increment the pointer
- Compare "left" character with "right" character
- Increment the pointer till while condition is met
```

```python
# O(n)
def is_palindrome(s):
    left, right = 0, len(s) - 1

    while left < right:
        while left < right and not s[left].isalnum():
            left += 1
        while left < right and not s[right].isalnum():
            right -= 1
        if s[left].lower() != s[right].lower():
            return False
        left += 1
        right -= 1
    return True

s = "A man, a plan, a canal: Panama"
print(is_palindrome(s))

s = "race a car"
print(is_palindrome(s))

s = " "
print(is_palindrome(s))
```
