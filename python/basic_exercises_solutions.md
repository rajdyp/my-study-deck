# Basic Exercises Solutions

1. Perform below multi line assignment in a single line.
```yaml
n = 0.125
m = "abc"
z = False
```

```python
n, m, z = 0.125, "abc", False
print(n)
print(m)
print(z)
```

2. Create a string `Hello, World!`
     - Just print `,` from the string
     - Get the characters from position 2 to position 5 (not included)
     - Print only the characters at even position
     - Replace `"H"` with `"Y"`
     - Split `My name is Rajdeep` to a list of substrings
     - Remove any whitespace from beginning or end of `" Hello, World! "`
     - Combine a list of strings `["ab", "cd", "ef"]` with an empty string delimitor

```python
print('\nCreate a string `Hello, World!`')
mystr = "Hello, World!"
print(mystr)

print('\nJust print `,` from the string')
print(mystr[5])

print('\nGet the characters from position 2 to position 5 (not included)')
print(mystr[2:5])

print('\nPrint only the characters at even position')
print(mystr[::2])

print('\nReplace `"H"` with `"Y"`')
print(mystr.replace("H", "Y"))

print('\nSplit "My name is Rajdeep" to a list of substrings')
mystr = "My name is Rajdeep"
print(mystr.split())

print('\nRemove any whitespace from beginning or end of `" Hello, World! "`')
mystr = " Hello, World! "
print(mystr.strip())

print('\nCombine a list of strings `["ab", "cd", "ef"]` with an empty string delimitor')
str_list = ["ab", "cd", "ef"]
print("".join(str_list))
```

3. Create a list of names containing `"John", "Alice", "Sarah", "Rajna", "George"` using list() constructor.
     - Print number of items in the list
     - Just print `"Alice", "Sarah", Rajna`
     - Retrieve `"George"`       
     - Retrieve `"Sarah"`
     - Replace `"John"` with `"Jenny"`
     - Replace `"Jenny", "Alice"` with `"John", "Maya"`
     - Add `"Simon"`
     - Add `"Betty"` before `"Sarah"`
     - Remove `"John"`
     - Remove element at index 2
     - Remove element at index 2
     - Remove the last element
     - Add list `fruits = ["apple", "banana", "cherry", "kiwi"]` to names
     - From above list, print all fruits that has `a` in its name using list comprehension
     - Reverse the order of the fruits list
     - Sort list numerically `num = [100, 50, 65, 82, 23 ]`
     - Sort above list in descending order
     - Join fruits and num list to a new list
     - Clear fruits list
     - Delete num list

```python
print('\n1. Create a list of names containing `"John", "Alice", "Sarah", "Rajna", "George"` using list() constructor\n')
names = list(("John", "Alice", "Sarah", "Rajna", "George"))
print(names)

print('\n2. Print number of items in the list\n')
print(f"No of items: {len(names)}")

print('\n3. Just print `"Alice", "Sarah", Rajna`\n')
print(names[1:4])

print('\n4. Retrieve `"George"`\n')
print(names[-1])

print('\n5. Retrieve `"Sarah"`\n')
print(names[2])

print('\n6. Replace `"John"` with `"Jenny"`\n')
names[0] = "Jenny"
print(names)

print('\n7. Replace `"Jenny", "Alice"` with `"John", "Maya"`\n')
names[0:2] = ["John", "Maya"]
print(names)

print('\n8. Add `"Simon"`\n')
names.append("Simon")
print(names)

print('\n9. Add `"Betty"` before `"Sarah"`\n')
names.insert(2, "Betty")
print(names)

print('\n10. Remove `"John"`\n')
names.remove("John")
print(names)

print('\n11. Remove element at index 2\n')
names.remove(names[2])
print(names)

print('\n12. Remove the last element\n')
names.pop()
print(names)

print('\n13. Add list `fruits = ["apple", "banana", "cherry", "kiwi"]` to names\n')
fruits = ["apple", "banana", "cherry", "kiwi"]
names.extend(fruits)
print(names)

print('\n14. From above list, print all fruits that has `a` in its name using list comprehension\n')
fruits = ["apple", "banana", "cherry", "kiwi"]
print([fruit for fruit in fruits if "a" in fruit])

print('\n15. Reverse the order of the fruits list\n')
fruits.reverse()
print(fruits)

fruits.sort(reverse=True)
print(fruits)

print('\n16. Sort list numerically `num = [100, 50, 65, 82, 23]`\n')
num = [100, 50, 65, 82, 23]
num.sort()
print(num)

print('\n17. Sort above list in descending order\n')
num = [100, 50, 65, 82, 23]
num.sort(reverse=True)
print(num)

print('\n18. Join fruits and num list to a new list\n')
new_list = fruits + num
print(new_list)

fruits.extend(num)
print(fruits)

print('\n19. Clear fruits list\n')
print(fruits)
fruits.clear()
print(fruits)

print('\n20. Delete num list\n')
print(num)
del num
print(num)
```

4. Create a tuple of names`"John", "Sarah", "Alice"` using tuple() constructor.
     - Print number of items in tuple
     - Create a tuple of single name `"Maya"`
     - Add name to names
     - Retrieve `"Sarah"`
     - Add `"Simon"`
     - Rmove `"John"`
     - Unpack tuple `fruits = ("apple", "banana", "kiwi")` as per their color and print their values
     - Delete fruits tuple

```python
print('\n1. Create a tuple of names`"John", "Sarah", "Alice"` using tuple() constructor\n')
names = tuple(("John", "Sarah", "Alice"))
print(names)

print('\n2. Create a tuple of single name `"Maya"`\n')
name = ("Maya",)
print(name)

print('\n3. Add name to names\n')
names += name
print(names)

print('\n4. Retrieve `"Sarah"`\n')
print(names[1])

print('\n5. Add `"Simon"``\n')
print("Cannot add items to a Tuple as it is immutable\n")

# workaround
add_name = list(names)
add_name.append("Simon")
print(tuple(add_name))

print('\n6. Rmove `"John"`\n')
print("Cannot remove items from a Tuple as it is immutable\n")

# workaround
rm_name = list(names)
rm_name.remove("John")
print(tuple(rm_name))

print('\n7. Unpack tuple `fruits = ("apple", "banana", "cherry")` as per their color and print their values\n')
fruits = ("apple", "banana", "cherry")
green, yellow, red = fruits
print(f"Green : {green}")
print(f"Yellow : {yellow}")
print(f"Red : {red}")

print('\n8. Delete fruits tuple\n')
print(fruits)
del fruits
print(fruits)
```

5. From below nested collections:
     - Retrieve `('Eternal Sunshine of the Spotless Mind', 2004)`
     - Retrieve `Eternal Sunshine of the Spotless Mind`

```yaml
movies = [
    ('Eternal Sunshine of the Spotless Mind', 2004),
    ('Memento', 2000)
]
```

```python
nested = """
movies = [
    ('Eternal Sunshine of the Spotless Mind', 2004),
    ('Memento', 2000)
]
"""

print(nested)
print("1. Retrieve `('Eternal Sunshine of the Spotless Mind', 2004)`")
print(movies[0])

print('\n2. Retrieve `Eternal Sunshine of the Spotless Mind`')
print(movies[0][0])
```

6. Create a dictionary called `student`, wherein student name is `"John Smith"` and his grades are `88, 76, 92, 85, 69`.
     - Print student grades
     - Add student age = 14
     - Print `John Smith is 14 years old and his grades are 88, 76, 92, 85, 69`
     - Create a dictionary called `school` using dict() constructor with school name and location'
     - Merge student dictionary with school dictionary     # check name key
     - Update student age to 18
     - Delete grades
     - List all keys
     - List all values
     - List all items
     - Iterate and print all keys
     - Iterate and print all values
     - Iterate and print both keys value pairs
     - Remove `location`
     - Remove last item
     - Remove all items
     - Delete student dictionary

```python
print('\n 1. Create a dictionary called `student`, wherein student name is `"John Smith"` and his grades are `88, 76, 92, 85, 69`')
student = {
    "name": "John Smith",
    "grades": [88, 76, 92, 85, 69]
}
print(student)

print('\n 2. Print student grades')
print(student["grades"])

print('\n 3. Add student age = 14')
student["age"] = 14
print(student)

print('\n 4. Print `John Smith is 14 years old and his grades are 88, 76, 92, 85, 69`')
print(f'{student["name"]} is {student["age"]} years old and his grades are {", ".join(map(str, student["grades"]))}')

print('\n 5. Create a dictionary called `school` using dict() constructor with school name and location')
school = dict({"name": "LES", "location": "Mirik"})
print(school)

print('\n 6. Merge student dictionary with school dictionary     # check name key')
student.update(school)
print(student)

# merge operator (|)
student = student | school
print(student)

print('\n 7. Update student age to 18')
student["age"] = 18
print(student)

print('\n 8. Delete grades')
del student["grades"]
print(student)

print('\n 9. List all keys')
print(student.keys())

print('\n 10. List all values')
print(student.values())

print('\n 11. List all items')
print(student.items())

print('\n 12. Iterate and print all keys')
for key in student.keys():
    print(key)

print('\n 13. Iterate and print all values')
for value in student.values():
    print(value)

print('\n 14. Iterate and print both keys value pairs')
for key, value in student.items():
    print(f"{key} : {value}")

print('\n 15. Remove `location`')
print(student.pop("location"))
print(student)

print('\n 16. Remove last item')
print(f"Last item: {student.popitem()}")
print(student)

print('\n 17. Remove all items')
student.clear()
print(student)

print('\n 18. Delete student dictionary')
print(student)
del student
print(student)
```

7. Create an empty set `set1`.
     - Add three items `"apple", "banana", "cherry"`
     - Print `"apple"` 
     - Create a second set `set2` using set() constructor with at least one common item with the first set
     - Find the union, symmetric difference, and intersection of the two sets
     - Add set1 and set2
     - Remove `"pineapple"`
     - Remove any random item
     - Remove all items
     - Delete set1

```python
print('\n1. Create an empty set `set1`')
set1 = set()
print(set1)

print('\n2. Add three items `"apple", "banana", "cherry"`')
set1.add("apple")
set1.add("banana")
set1.add("cherry")
print(set1)

print('\n3. Print `"apple"`')
print("Cannot access items in a set using index or key as it is unordered")

print('\n4. Create a second set `set2` using set() constructor with at least one common item with the first set')
set2 = set(("apple", "mango", "pineapple"))
print(set2)

print('\n5. Find the union, symmetric difference, and intersection of the two sets')
print(f"Union                   : {set1.union(set2)}")
print(f"Symmetric difference    : {set1.symmetric_difference(set2)}")
print(f"Intersection            : {set1.intersection(set2)}")

print('\n6. Add set1 and set2')
set1.update(set2)
print(set1)

print('\n7. Remove `"pineapple"`')
set1.remove("pineapple")
print(set1)

print('\n8. Remove any random item')
set1.pop()
print(set1)

print('\n9. Remove all items')
set1.clear()
print(set1)

print('\n10. Delete set1')
print(set1)
del set1
print(set1)
```

8. Create double-ended queue `[4, 5, 6]`.
     - Append `7` to the right
     - Append `3` to the left
     - Append `[8, 9, 10]` to right
     - Append `[1, 2]` to left
     - Insert `-1` at index 5
     - Remove element from the right end
     - Remove element from the left end
     - Remove `-1`
     - Count the number of times `5` occurs
     - Return index of '7'
     - Rotate the deque three times to the right
     - Reverse the whole deque

```python
print('\nCreate double-ended queue `[4, 5, 6]`.')
from collections import deque
dq = deque([4, 5, 6])
print(dq)

print('\nAppend `7` to the right')
dq.append(7)
print(dq)

print('\nAppend `3` to the left')
dq.appendleft(3)
print(dq)

print('\nAppend `[8, 9, 10]` to right')
dq.extend([8, 9, 10])
print(dq)

print('\nAppend `[1, 2]` to left')
dq.extendleft([1, 2])
print(dq)

print('\nInsert `-1` at index 5')
dq.insert(5, -1)
print(dq)

print('\nRemove element from the right end')
dq.pop()
print(dq)

print('\nRemove element from the left end')
dq.popleft()

print('\nRemove `-1`')
dq.remove(-1)
print(dq)

print('\nCount the number of times `5` occurs')
print(dq.count(5))

print('\nReturn index of `7`')
print(dq)
print(dq.index(7))

print('\nRotate the deque three times to the right')
dq.rotate(3)
print(dq)

print('\nReverse the whole deque')
dq.reverse()
print(dq)
```

6. Create a sequence of numbers using range:
     - Ask user to enter a number
     - Inform the user whether or not the number was within the specified range
     - Also tell the user if their number was too high or too low
```python
num = range(5, 11)
within_range = False

while within_range == False:
    n = int(input("Enter any number between 0 to 20: "))
    if n >= num[0] and n <= num[-1]:        # if n in num
        print("Within range!")
        within_range = True
    elif n >= 0 and n < num[0]:
        print("Too low!")
    elif n > num[-1] and n <= 20:
        print("Too high!")
    else:
        print("Out of range!")
```

7. Split `text = "was it a car"` to  a list `'w', 'a', 's', 'i', 't', 'a', 'c', 'a', 'r'` (Try same using list comprehension as well)
     - Convert above list to a string of characters `w, a, s, i, t, a, c, a, r`
```python
text = "was it a car"
mylist = []
for i in text:          # for i in text.replace(" ", "")
    if i != " ":
        mylist.append(i)

print(mylist)
print(", ".join(mylist))

# shorter version
text = "was it a car"
mylist = list(text.replace(" ", ""))
print(mylist)
print(", ".join(mylist))
```
```python
# list comprehension 
text = "was it a car"
mylist = [i for i in text if i != " "]
print(mylist)
print(", ".join(mylist))
```

8. Print first and last name `Rajdeep Rai` without using string concatenation.
```python
print("Rajdeep", end=" ")
print("Rai")
```

9. If integer `n = 5`, print `12345`. Do the same without using any string join() method.
```python
n = 5
mylist = []
for i in range(1, n + 1):
    mylist.append(i)          # mylist.append(str(i))
print("".join(map(str, mylist)))
```
```python
# without using join()
n = 5
for i in range(1, n + 1):
    print(i, end='')
print(" ")
```

10. If integer `n = 5`, perform backwards iteration and print `5 4 3 2 1`.
```python
n = 5
for i in reversed(range(1, n+1)):          # for i in range(n, 0, -1):
    print(i, end=" ")
print(" ")
```
```python
n = 5
mylist = []
for i in range(n, 0, -1):
    mylist.append(str(i))
print(" ".join(mylist))
```
```python
n = 5
for i in reversed(range(1, n+1)):
    if i != n - (n - 1):
        print(i, end=" ")
    if i == n - (n - 1):
        print(i)
```

11. Print second highest value in the list `[2, 3, 8, 8, 8, 6, 6, 5]`
```python
mylist = [2, 3, 8, 8, 8, 6, 6, 5]
unique_list = sorted(set(mylist))
print(unique_list[-2])
```
```python
mylist = [2, 3, 8, 8, 8, 6, 6, 5]
mylist = list(dict.fromkeys(mylist))
mylist.sort()
print(mylist[-2])
```

12. Convert `text = "Hello word !"` into `helloworld!`.
```python
text = "Hello word !"
print(text.lower().replace(" ", ""))
```

13. Convert given list `numbers = [1, 2, 3, 4, 5]` to `1, 2, 3, 4, 5`
```python
numbers = [1, 2, 3, 4, 5]
print(", ".join(map(str, numbers)))
```
```python
numbers = [1, 2, 3, 4, 5]
str_numbers = []
for i in numbers:
    str_numbers.append(str(i))

print(", ".join(str_numbers))
```
```python
# list comprehension 
numbers = [1, 2, 3, 4, 5]
numbers = ", ".join([str(i) for i in numbers])
print(numbers)
```

14. Reverse the string `"Hello World"`
```python
print("Hello World"[::-1])
```

15. Remove duplicates from the given list: `mylist = ["a", "b", "a", "c", "c"]`
```python
mylist = ["a", "b", "a", "c", "c"]
print(list(dict.fromkeys(mylist)))
```
```python
mylist = ["a", "b", "a", "c", "c"]
mylist = list(set(mylist))
print(sorted(mylist))
```

16. Split integer `1234` into digits `1 2 3 4`
```python
num = 1234
list = []
for i in str(num):
    list.append(str(i))
print(list)
print(" ".join(list))
```
```python
# list comprehension

num = 1234
mylist = [i for i in str(num)]
print(" ".join(mylist))
```

17. Find sum of digits of a number `888`.
```python
n = 888
sum = 0
for i in str(n):
    sum += int(i)
print(sum)
```

18. Break any text to a list of words.
```python
text = "what a beautiful day"
print(text.split())
```

19. Add tuple to an existing list.
```python
fruits = ["apple", "banana", "orange"]
veges = ("carrot", "cucumber")

fruits.extend(veges)
print(fruits)
```
```python
movies = [
    ("Eternal Sunshine of the Spotless Mind", 20000000),
    ("Memento", 9000000),
]
new_movie = ("Titanic", 800000000)

movies.append(new_movie)
print(movies)
```

20. Convert list `mylist = ["abc", "xyz", "qpr"]` to tuple and tuple `mytuple = ("abc", "xyz", "qpr")` to list.
```python
mylist = ["abc", "xyz", "qpr"]
mytuple = tuple(mylist)
print(mytuple)

mytuple = ("abc", "xyz", "qpr")
mylist = list(mytuple)
print(mylist)
```

21. For the sequence of digits `5893804115457289`, take each digits at even indices (0, 2, 4, 6, etc.) and double them.
```python
digits = 5893804115457289
for index, num in enumerate(str(digits)):
    if index % 2 == 0:
        double_num = int(num) * 2
        print(double_num)
```

22. Reverse the order of digits `5893804115457289` using list. Re-reverse the list using reversed method. 
```python
digits = 5893804115457289
mylist = list(str(digits))
print(mylist)
mylist.reverse()
print(mylist)
re_reversed = list(reversed(mylist))
print(re_reversed)
```

23. Print values in list along with its index `nums = [2,7,11,15]`
```python
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
```python
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

25. Using max() function:
     - Find the maximum element in an iterable: `numbers = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]`
     - Find the maximum length element: `words = ["apple", "banana", "cherry", "date"]`
     - Find the maximum value from multiple arguments: `42, 17, 56, 29, 87`
     - Find the maximum key in a dictionary: `square = {2: 4, -3: 9, -1: 1, -2: 4}`
     - Find maximum value (or default value if empty): `empty_list = []`

```python
# find the maximum element in an iterable: `numbers = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]`

numbers = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]
max_element = max(numbers)
print(max_element)

# find the maximum length element: `words = ["apple", "banana", "cherry", "date"]`

words = ["apple", "banana", "cherry", "date"]
max_len = max(words, key=len)
print(max_len)

# find the maximum value from multiple arguments: `42, 17, 56, 29, 87`

max_value = max(42, 17, 56, 29, 87)
print(max_value)

# find the maximum key in a dictionary: `square = {2: 4, -3: 9, -1: 1, -2: 4}`

square = {2: 4, -3: 9, -1: 1, -2: 4}
max_key = max(square, key=lambda k: square[k])
print(max_key)

# find maximum value (or default value if empty): `empty_list = []`

empty_list = []
handle_error = max(empty_list, default=0)
print(handle_error)
```

26. `square = {2: 4, -3: 9, -1: 1, -2: 4}` Find `a.` Largest key. `b.` Key whose value is the largest. `c.` Get the largest value.
```python
square = {2: 4, -3: 9, -1: 1, -2: 4}

key1 = max(square)
print(key1)

key2 = max(square, key=lambda k: square[k])
print(key2)

print(square[key2])
```

27. Take the list `numbers = [1, 2, 3, 4, 5]` and print the numbers on a single line with pipe (|) characters between each number.
```python
numbers = [1, 2, 3, 4, 5]
str_numbers = []
for i in numbers:
    str_numbers.append(str(i))

print(" | ".join(str_numbers))
```
```python
numbers = [1, 2, 3, 4, 5]
print(*numbers, sep=" | ")
```

28. Create a sorted list from 0 to 50.
```python
numbers = list(range(51))
print(numbers)
```

29. Nested list: `students = [['Harry', 37.21], ['Berry', 37.21], ['Tina', 37.2], ['Akriti', 41], ['Harsh', 39]]`
     - Sort the grades in ascending order
     - Sort the grades in ascending order and only unique values
     - Sort the names in decending order
```python
students = [['Harry', 37.21], ['Berry', 37.21], ['Tina', 37.2], ['Akriti', 41], ['Harsh', 39]]
grades = sorted([student[1] for student in students])
unique_grades = sorted(list(set([student[1] for student in students])))
names = sorted([student[0] for student in students], reverse=True)
print(grades)
print(unique_grades)
print(names)
```
