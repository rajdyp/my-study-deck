# Basic Exercises Solutions

4. Print `John Smith is 14 years old and his grades are 88, 76, 92, 85, 69`
```yaml
print(f"{student['name']} is {student['age']} years old and his grades are {', '.join(map(str, student['grades']))}")
```

6. Create a sequence of numbers using range:
     - Ask user to enter a number
     - Inform the user whether or not the number was within the specified range
     - Also tell the user if their number was too high or too low
```yaml
num = range(5, 11)
within_range = False

while within_range == False:
    n = int(input("Enter any number between 0 to 20: "))
    if n >= num[0] and n <= num[-1]:        # if n in num
        print("Within range!")
        within_range = True
    elif n < num[0]:
        print("Too low!")
    elif n > num[-1] and n < 20:
        print("Too high!")
    else:
        print("Out of range!")
```

7. Split `text = "was it a car"` to  a list `'w', 'a', 's', 'i', 't', 'a', 'c', 'a', 'r'` (Try same using list comprehension as well)
     - Convert above list to a string of characters `w, a, s, i, t, a, c, a, r`
```yaml
text = "was it a car"
mylist = []
for i in text:          # for i in text.replace(" ", "")
    if i != " ":
        mylist.append(i)

print(mylist)
print(", ".join(mylist))
```
```yaml
# list comprehension 
text = "was it a car"
mylist = [i for i in text if i != " "]
print(mylist)
print(", ".join(mylist))
```

8. Print first and last name `Rajdeep Rai` without using string concatenation.
```yaml
print("Rajdeep", end=" ")
print("Rai")
```

9. If integer `n = 5`, print `12345`. Do the same without using any string join() method.
```yaml
n = 5
mylist = []
for i in range(1, n + 1):
    mylist.append(i)
print("".join(map(str, mylist)))
```
```yaml
# without using join()
n = 5
for i in range(1, n + 1):
    print(i, end='')
```

10. If integer `n = 5`, perform backwards iteration and print `5 4 3 2 1`.
```yaml
n = 5
for i in reversed(range(1, n+1)):
    print(i, end=" ")
```
```yaml
n = 5
for i in reversed(range(1, n+1)):
    if i != n - (n - 1):
        print(i, end=" ")
    if i == n - (n - 1):
        print(i)
```

11. Print second highest value in the list `[2, 3, 8, 8, 8, 6, 6, 5]`
```yaml
mylist = [2, 3, 8, 8, 8, 6, 6, 5]
unique_list = list(set(mylist))
print(unique_list[-2])
```
```yaml
mylist = [2, 3, 8, 8, 8, 6, 6, 5]
mylist = list(dict.fromkeys(mylist))
mylist.sort()
print(mylist[-2])
```

12. Convert `text = "Hello word !"` into `helloworld!`.
```yaml
text = "Hello word !"
print(text.lower().replace(" ", ""))
```

13. Convert given list `numbers = [1, 2, 3, 4, 5]` to `1, 2, 3, 4, 5`
```yaml
numbers = [1, 2, 3, 4, 5]
str_numbers = []
for i in numbers:
    str_numbers.append(str(i))

print(", ".join(str_numbers))
```
```yaml
# list comprehension 
numbers = [1, 2, 3, 4, 5]
str_numbers = ", ".join([str(i) for i in numbers])
print(str_numbers)
```

14. Reverse the string `"Hello World"`
```yaml
print("Hello World"[::-1])
```

15. Remove duplicates from the given list: `mylist = ["a", "b", "a", "c", "c"]`
```yaml
mylist = ["a", "b", "a", "c", "c"]
print(list(dict.fromkeys(mylist)))
```

16. Split integer `1234` into digits `1 2 3 4`
```yaml
num = 1234
list = []
for i in str(num):
    list.append(str(i))
print(list)
print(" ".join(list))
```

17. Find sum of digits of a number `888`.
```yaml
n = 888
sum = 0
for i in str(n):
    sum += int(i)
print(sum)
```

18. Break any text to a list of words.
```yaml
text = "what a beautiful day"
print(text.split())
```

19. Add tuple to an existing list.
```yaml
fruits = ["apple", "banana", "orange"]
veges = ("carrot", "cucumber")

fruits.extend(veges)
print(fruits)
```
```yaml
movies = [
    ("Eternal Sunshine of the Spotless Mind", 20000000),
    ("Memento", 9000000),
]
new_movie = ("Titanic", 800000000)

movies.append(new_movie)
print(movies)
```

20. Convert list `mylist = ["abc", "xyz", "qpr"]` to tuple and tuple `mytuple = ("abc", "xyz", "qpr")` to list.
```yaml
mylist = ["abc", "xyz", "qpr"]
mytuple = tuple(mylist)
print(mytuple)

mytuple = ("abc", "xyz", "qpr")
mylist = list(mytuple)
print(mylist)
```

21. For the sequence of digits `5893804115457289`, take each digits at even indices (0, 2, 4, 6, etc.) and double them.
```yaml
digits = 5893804115457289
for index, num in enumerate(str(digits)):
    if index % 2 == 0:
        double_num = int(num) * 2
        print(double_num)
```

22. Reverse the order of digits `5893804115457289` using list.
```yaml
num = 5893804115457289
mylist = list(str(5893804115457289))
mylist.reverse()
print(mylist)
```

23. Print values in list along with its index `nums = [2,7,11,15]`
```yaml
nums = [2,7,11,15]
for index, num in enumerate(nums):
    print(f"{index} : {num}")
```

24. Check for leap year.
```yaml
In the Gregorian calendar, three conditions are used to identify leap years:
- The year can be evenly divided by 4, is a leap year, unless
- The year can be evenly divided by 100, it is NOT a leap year, unless
- The year is also evenly divisible by 400. Then it is a leap year.
```
```yaml
year = int(input("Enter any year: "))
if year % 4 == 0:
    if year % 100 == 0:
        if year % 400 == 0:
            print("Leap year")
        else:
            print("Not a leap year")
    else:
        print("Leap year")
else:
    print("Not a leap year")
```

25. `square = {2: 4, -3: 9, -1: 1, -2: 4}` Find `a.` Largest key. `b.` Key whose value is the largest. `c.` Get the largest value.
```yaml
square = {2: 4, -3: 9, -1: 1, -2: 4}

key1 = max(square)
print(key1)

key2 = max(square, key=lambda k: square[k])
print(key2)

print(square[key2])
```

26. Take the list `numbers = [1, 2, 3, 4, 5]` and print the numbers on a single line with pipe (|) characters between each number.
```yaml
numbers = [1, 2, 3, 4, 5]
str_numbers = []
for i in numbers:
    str_numbers.append(str(i))

print(" | ".join(str_numbers))
```
```yaml
numbers = [1, 2, 3, 4, 5]
print(*numbers, sep=" | ")
```

27. 
