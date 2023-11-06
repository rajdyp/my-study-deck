# NeetCode

## Blind75

<details>
<summary> Contains duplicate </summary>

```yaml
Given an integer array nums, return true if any value appears at least twice in the array, and return false if every
element is distinct.

Example 1:
Input: nums = [1,2,3,1]
Output: true

Example 2:
Input: nums = [1,2,3,4]
Output: false

Example 3:
Input: nums = [1,1,1,3,3,4,3,2,4,2]
Output: true

Constraints:
- 1 <= nums.length <= 105
- -109 <= nums[i] <= 109
```

> [Problem solution](https://github.com/rajdyp/rajdyp.github.io/blob/master/python/solutions/contains_duplicate.md)
</details>


<details>
<summary> Valid anagram </summary>

```yaml
Given two strings s and t, return true if t is an anagram of s, and false otherwise.
An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all
the original letters exactly once.

Example 1:
Input: s = "anagram", t = "nagaram"
Output: true

Example 2:
Input: s = "rat", t = "car"
Output: false
 
Constraints:
- 1 <= s.length, t.length <= 5 * 104
- s and t consist of lowercase English letters.
```

> [Problem solution](https://github.com/rajdyp/rajdyp.github.io/blob/master/python/solutions/valid_anagram.md)
</details>


<details>
<summary> Two sum </summary>

```yaml
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to
target. You may assume that each input would have exactly one solution, and you may not use the same element twice.
You can return the answer in any order.

Example 1:
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].

Example 2:
Input: nums = [3,2,4], target = 6
Output: [1,2]

Example 3:
Input: nums = [3,3], target = 6
Output: [0,1]
 
Constraints:
- 2 <= nums.length <= 104
- -109 <= nums[i] <= 109
- -109 <= target <= 109
- Only one valid answer exists.
```

> [Problem solution](https://github.com/rajdyp/rajdyp.github.io/blob/master/python/solutions/two_sum.md)
</details>


<details>
<summary> Valid palindrome </summary>

```yaml
A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all
non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and
numbers. Given a string s, return true if it is a palindrome, or false otherwise.

Example 1:
Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.

Example 2:
Input: s = "race a car"
Output: false
Explanation: "raceacar" is not a palindrome.

Example 3:
Input: s = " "
Output: true
Explanation: s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.

Constraints:
- 1 <= s.length <= 2 * 105
- s consists only of printable ASCII characters.
```

> [Problem solution](https://github.com/rajdyp/rajdyp.github.io/blob/master/python/solutions/valid_palindrome.md)
</details>


<details>
<summary> Best time to buy and sell stock </summary>

```yaml
You are given an array prices where prices[i] is the price of a given stock on the ith day. You want to maximize
your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.
Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

Example 1:
Input: prices = [7,1,5,3,6,4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.

Example 2:
Input: prices = [7,6,4,3,1]
Output: 0
Explanation: In this case, no transactions are done and the max profit = 0.

Constraints:
- 1 <= prices.length <= 105
- 0 <= prices[i] <= 104
```

> [Problem solution](https://github.com/rajdyp/rajdyp.github.io/blob/master/python/solutions/best_time_to_buy_sell_stock.md)
</details>
