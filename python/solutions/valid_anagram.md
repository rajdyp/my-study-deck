## Valid anagram
```yaml
Need to meet two conditions for anagram:
- Both string (s and t) length should be equal
- Number of individual characters should be equal
```
```python
# O(n)
def is_anagram(s, t):
    if len(s) != len(t):
        return False
    
    s_count = {}
    t_count = {}

    for char in s:
        s_count[char] = s_count.get(char, 0) + 1

    for char in t:
        t_count[char] = t_count.get(char, 0) + 1

    return s_count == t_count

s = "anagram"
t = "nagaram"
print(is_anagram(s, t))
```
