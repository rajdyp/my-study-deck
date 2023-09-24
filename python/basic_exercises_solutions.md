# Basic Exercises Solutions

6. Create a sequence of numbers using range:
     - Ask user to enter a number
     - Inform the user whether or not the number was within the specified range
     - Also tell the user if their number was too high or too low
```yaml
within_range = False 
numbers = range(5, 15)

while within_range == False:
    num = int(input("Enter any number below 20: "))
    if num in numbers:
        print("Within range!")
        within_range = True
    if num > numbers[-1]:
        print("Too high")
    if num < numbers[0]:
        print("Too low")
```

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

new_movie = tuple(["Titanic", 800000000])    # new_movie = ("Titanic", 800000000)
movies.append(new_movie)
print(movies)
```

8. Convert list to tuple and tuple to list.
```yaml
mylist = ["abc", "xyz", "qpr"]
mytuple = tuple(mylist)
print(mytuple)
```

9. For the given sequence of digits `5893804115457289`, take the digits at each of the even indices (0, 2, 4, 6, etc.) and double them.
```yaml
num = 5893804115457289
str_num = str(num)
for index, i in enumerate(str_num):
    if index % 2 == 0:
        double_num = int(i) * 2
        print (double_num)
```

10. Reverse the order of the digits `5893804115457289` using list.
```yaml
num = 5893804115457289
mylist = list(str(5893804115457289))
mylist.reverse()
print(mylist)
```

11. 
