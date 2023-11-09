## Maintaining Two Variables (Largest and Second Largest)

**Use case:** Used for finding and tracking the largest and second largest elements in a collection without having to sort the entire array.

```yaml
# flow chart
Start

Initialize largest and secondLargest to negative infinity

For each number in the array:
   |
   |---> If the number is greater than largest:
   |     |
   |     |---> Update secondLargest to the current largest
   |     |
   |     |---> Update largest to the current number
   |
   |---> Else if the number is greater than secondLargest:
         |
         |---> Update secondLargest to the current number

Repeat for all numbers in the array

Result: 
   |
   |---> Largest contains the largest element
   |---> SecondLargest contains the second largest element

End
```

```yaml
# condensed steps

Step 1: Initialization:
Start by initializing two variables, often named "current" and "previous."

Step 2: Traverse the Array
Iterate through the array of numbers.

Step 3: Update `l` and `sl`
- If current number is greater than `l`, update `sl` to `l` and set `l` to current number.
- If current number is greater than `sl` but not `l`, update `sl` to current number.

Step 4: Continue Iterating
Repeat step 3 for all elements in the array.

Step 5: Final Result
After processing all elements, `l` contains the largest element, and `sl` contains the second largest element.

Step 6: Handling Edge Cases
Consider how to handle duplicates or specific cases based on your requirements.
```

```yaml
Some common problem where the two pointers technique is applicable:

- Two Sum Problems:
  - Finding pairs of elements that sum up to a specific target value.

- Three Sum Problems:
  - Identifying triplets that sum up to a target value.

- Subarray Problems:
  - Determining subarrays that meet certain conditions (e.g., maximum sum subarray).

- Palindrome Problems:
  - Checking whether a string or sequence is a palindrome.

- Merge or Intersection Problems:
  - Merging or finding intersections between two sorted arrays or lists.

- Reverse Problems:
  - Reversing elements or characters within a data structure.

- Cycle Detection:
  - Detecting cycles in linked lists or arrays.

- Remove Duplicates:
  - Removing duplicates from a sorted or unsorted array.

- Container with Most Water:
  - Finding the two lines that together with the x-axis forms a container that contains the most water.

- Two Pointers on Two Arrays:
  - Solving problems that involve two separate arrays or lists (e.g., merging two sorted arrays).

- Trapping Rainwater:
  - Calculating the amount of rainwater that can be trapped between bars.

- Move Zeros:
  - Rearranging an array to move all zeros to the end while maintaining relative order of non-zero elements.

- Intersection of Two Linked Lists:
  - Finding the node where two linked lists intersect.

- Partitioning Problems:
  - Partitioning an array or list based on a certain condition (e.g., Dutch National Flag problem).

- Closest Pair of Points:
  - Finding the pair of points with the smallest distance in a set of points.

- Longest Substring Without Repeating Characters:
  - Finding the longest substring without repeating characters in a string.

- Valid Parentheses:
  - Checking if a string of parentheses is valid.

- Longest Palindromic Substring:
  - Finding the longest palindromic substring within a string.

- Kth Smallest Element in a Matrix:
  - Finding the Kth smallest element in a sorted matrix.

- Array Segmentation:
  - Dividing an array into segments with specific properties.
```

### Detailed steps

The "two pointers" technique is a common approach used in computer programming to solve a variety of problems, particularly those that involve searching, comparing, or manipulating data in a linear or sequential manner. This technique is often used with arrays or linked lists. Here's a step-by-step explanation of how the two pointers technique works:

- Step 1: Initialize Pointers
    - Start by defining two pointers, usually named left and right.
    - Set left to the beginning or the first element of the data structure (e.g., the first element of an array) and right to the end or the last element.

- Step 2: Define the Problem Constraints
    - Clearly understand the problem constraints and requirements. You need to know what you're trying to achieve with the two pointers technique.
    - Understand what conditions or criteria you need to satisfy to solve the problem.

- Step 3: Loop or Iterate
    - Use a loop, such as a while loop or a for loop, to traverse the data structure.
    - The loop condition should depend on the problem's constraints or requirements.

- Step 4: Move the Pointers
    - In each iteration of the loop, move the pointers according to the problem's requirements.
    - You can move both pointers towards each other, or you can move one pointer while keeping the other one stationary.
    - The movement of the pointers depends on the specific problem you're trying to solve.

- Step 5: Check the Condition
    - After moving the pointers, check whether they satisfy the condition or criteria required to solve the problem.
    - If the condition is met, you can perform the necessary operations, such as returning a result, updating variables, or storing values.

- Step 6: Repeat Until Termination
    - Continue the loop until you have processed the entire data structure or until you have satisfied the problem's constraints.
    - Make sure to handle edge cases and termination conditions carefully to avoid infinite loops.

- Step 7: Finalize
    - Once the loop is complete, you can finalize the solution by returning the desired output or result.

The key to the two pointers technique is the efficient traversal and manipulation of data structures by maintaining two pointers, usually in opposite directions or with one stationary. This approach is especially useful for problems that involve searching for pairs, subarrays, or subsequences that satisfy certain conditions, and it often leads to more efficient solutions than other methods.

> Here's an example problem that illustrates the use of the two pointers technique:
> 
> Problem: Given a sorted array of integers, find a pair of elements that sum up to a specific target value.
> 
> Solution using Two Pointers:
> 
> - Initialize left at the beginning of the array and right at the end of the array.
> - Use a while loop with the condition left < right.
> - Calculate the sum of the elements at left and right.
> - If the sum is equal to the target value, return the indices of left and right.
> - If the sum is less than the target, increment left.
> - If the sum is greater than the target, decrement right.
> - Repeat steps 3-6 until you find the pair or determine that no such pair exists.