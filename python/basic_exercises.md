# Basic Exercises

1. Perform below multi line assignment in a single line.
```yaml
n = 0.125
m = "abc"
z = False
```

2. Create a string `Hello, World!`
     - Just print `,` from the string
     - Get the characters from position 2 to position 5 (not included)
     - Print only the characters at even position
     - Replace `"H"` with `"Y"`
     - Split "My name is Rajdeep" to a list of substrings
     - Remove any whitespace from beginning or end of `" Hello, World! "`
     - Combine a list of strings `["ab", "cd", "ef"]` with an empty string delimitor

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
     - Remove the last element
     - Add list `fruits = ["apple", "banana", "cherry", "kiwi"]` to names
     - From above list, print all fruits that has `a` in its name using list comprehension
     - Reverse the order of the fruits list
     - Sort list numerically `num = [100, 50, 65, 82, 23]`
     - Sort above list in descending order
     - Join fruits and num list to a new list
     - Clear fruits list
     - Delete num list

4. Create a tuple of names`"John", "Sarah", "Alice"` using tuple() constructor.
     - Print number of items in tuple
     - Create a tuple of single name `"Maya"`
     - Add name to names
     - Retrieve `"Sarah"`
     - Add `"Simon"`
     - Rmove `"John"`
     - Unpack tuple `fruits = ("apple", "banana", "cherry")` as per their color and print their values
     - Delete fruits tuple

5. From nested collections:
     - Retrieve `('Eternal Sunshine of the Spotless Mind', 2004)`
     - Retrieve `Eternal Sunshine of the Spotless Mind`

6. Create a dictionary called `student`, wherein student name is `"John Smith"` and his grades are `88, 76, 92, 85, 69`.
     - Print student grades
     - Add student age = 14
     - Print `John Smith is 14 years old and his grades are 88, 76, 92, 85, 69`
     - Create a dictionary called `school` using dict() constructor with school name and location
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
     - Return index of '7' if found between index 4 and 6
     - Rotate the deque three times to the right
     - Reverse the whole deque

9. Create a min-heap `myheap` and add elements `1, 2, 7, 4`.
     - Print the smallest element
     - Find 3 smallest and 3 largest elements in `[10, 3, 5, 8, 1, 6, 9, 2]`
     - Convert a list `[1, 4, 5, 9, 8, 5]` into a min-heap
     - Replace smallest element with `2`

10. Write a function to add two numbers and print the result. 
     - Retrun the value and use it to print the result
     - Write a function to add `n` numbers
     - Write a function to return total number of fruits
     - Write a lambda function to print `Hey there, Raj`

11. Create a file `test.txt` and write `What is this life if, full of care,`.
     - Append `We have no time to stand and stare?` to the file
     - Read the file and print all its contents
     - Read the file and just print first line
     - Try to create file `test.txt` and return an error if the file exists
     - Delete `test.txt` and check if file exists

12. Create a class named Person, use the __init__() function to assign values for name and age.
     - Add a function that prints a greeting, and execute it on the p1 object

13. Create a sequence of numbers using range:
     - Ask user to enter a number
     - Inform the user whether or not the number was within the specified range
     - Also tell the user if their number was too high or too low

14. Split text = "was it a car" to a list 'w', 'a', 's', 'i', 't', 'a', 'c', 'a', 'r' (Try same using list comprehension as well)
     - Convert above list to a string of characters w, a, s, i, t, a, c, a, r

15. Print first and last name `Rajdeep Rai` without using string concatenation.

16. If integer `n = 5`, print 12345. Do the same without using any string join() method.

17. If integer `n = 5`, perform backwards iteration and print `5 4 3 2 1`.

18. Print second highest value from the list `[2, 3, 8, 8, 8, 6, 6, 5]`.

19. Convert `text = "Hello word !"` into `helloworld!`.

20. Convert given list `numbers = [1, 2, 3, 4, 5]` to `1, 2, 3, 4, 5`

21. Reverse the string `"Hello World"`

22. Remove duplicates from the given list: `mylist = ["a", "b", "a", "c", "c"]`

23. Split integer `1234` into digits `1 2 3 4`

24. Find sum of digits of a number `888`.

25. Break any text to a list of words.

26. Add tuple to an existing list.

```yaml
fruits = ["apple", "banana", "orange"]
veges = ("carrot", "cucumber")
```
```yaml
movies = [
    ("Eternal Sunshine of the Spotless Mind", 20000000),
    ("Memento", 9000000),
]
new_movie = ("Titanic", 800000000)
```
27. Convert list mylist = ["abc", "xyz", "qpr"] to tuple and tuple mytuple = ("abc", "xyz", "qpr") to list.

28. For the sequence of digits `5893804115457289`, take each digits at even indices (0, 2, 4, 6, etc.) and double them.

29. Reverse the order of digits `5893804115457289` using list. Re-reverse the list using reversed method. 

30. Print values in list along with its index `nums = [2,7,11,15]`

31. Check for leap year. In the Gregorian calendar, three conditions are used to identify leap years:
     - The year can be evenly divided by 4, is a leap year, unless
     - The year can be evenly divided by 100, it is NOT a leap year, unless
     - The year is also evenly divisible by 400. Then it is a leap year.

32. Using max() function:
     - Find the maximum element in an iterable: `numbers = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]`
     - Find the maximum length element: `words = ["apple", "banana", "cherry", "date"]`
     - Find the maximum value from multiple arguments: `42, 17, 56, 29, 87`
     - Find the maximum key in a dictionary: `square = {2: 4, -3: 9, -1: 1, -2: 4}`
     - Find maximum value (or default value if empty): `empty_list = []`

33. `square = {2: 4, -3: 9, -1: 1, -2: 4}` Find `a.` Largest key. `b.` Key whose value is the largest. `c.` Get the largest value.

34. Take the list `numbers = [1, 2, 3, 4, 5]` and print the numbers on a single line with pipe (|) characters between each number. 

35. Create a sorted list from 0 to 50.

36. Nested list: `students = [['Harry', 37.21], ['Berry', 37.21], ['Tina', 37.2], ['Akriti', 41], ['Harsh', 39]]`
     - Sort the grades in ascending order
     - Sort the grades in ascending order and only unique values
     - Sort the names in decending order
