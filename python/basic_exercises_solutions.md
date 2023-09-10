# Basic Exercises Solutions

1. Convert given list `numbers = [1, 2, 3, 4, 5]` to `1, 2, 3, 4, 5`
```yaml
numbers = [1, 2, 3, 4, 5]
list = ", ".join([str(i) for i in numbers])
print(list)
```

2. Reverse the string `"Hello World"`
```yaml
text = "Hello World"
print(text[::-1])
```

3. Remove duplicates from the given list: `mylist = ["a", "b", "a", "c", "c"]`
```yaml
mylist = ["a", "b", "a", "c", "c"]
new_list = list(dict.fromkeys(mylist))
print(new_list)
```

4. Split integer `1234` into digits `1 2 3 4`
```yaml
num = 1234
list = []
for i in str(num):
    list.append(i)
digits = " ".join([str(i) for i in list])
print(digits)
```

5. Find sum of digits of a number `888`.
```yaml
n = 888
sum = 0
for i in str(n):
    sum += int(i)
print(sum)
```

6. Break any text to a list of words.
```yaml
text = "what a beautiful day"
print(text.split())
```

7. Add tuple to an existing list.
```yaml
movies = [
    ("Eternal Sunshine of the Spotless Mind", 20000000),
    ("Memento", 9000000),
]

new_movie = tuple(["Titanic", 800000000])
movies.append(new_movie)
print(movies)
```

8. 
