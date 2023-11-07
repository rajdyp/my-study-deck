## Contains duplicate

```python
# O(n)
def is_valid(s):
    stack = []      # store open bracket
    mymap = {")": "(", "]": "[", "}": "{"}

    for char in s:
        if char in mymap:
            if len(stack) > 0:
                top = stack.pop()
            if top != mymap[char]:
                return False
        else:
            stack.append(char)
        
    if len(stack) == 0:
        return True
    return False

# Example usage
s1 = "()"
print(is_valid(s1))

s2 = "()[]{}"
print(is_valid(s2))

s3 = "(]"
print(is_valid(s3))

s4 = "("
print(is_valid(s4))

s5 = "(({[]}))"
print(is_valid(s5))
```
