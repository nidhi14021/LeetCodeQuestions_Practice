# 1662. Check If Two String Arrays are Equivalent

**Problem Link:** https://leetcode.com/problems/check-if-two-string-arrays-are-equivalent/

## Problem
Given two string arrays `word1` and `word2`, return `true` if the two arrays represent the same string, and `false` otherwise.

A string is represented by concatenating the elements of the array in order.

## Approach
- Create two empty strings `s1` and `s2`.
- Concatenate all strings from `word1` into `s1`.
- Concatenate all strings from `word2` into `s2`.
- Compare the two final strings.
- Return `True` if they are equal; otherwise, return `False`.

## Solution

```python
class Solution:
    def arrayStringsAreEqual(self, word1: List[str], word2: List[str]) -> bool:
        s1 = ""
        s2 = ""

        for word in word1:
            s1 += word

        for word in word2:
            s2 += word

        return s1 == s2
```

## Example 1

**Input:**

```text
word1 = ["ab", "c"]
word2 = ["a", "bc"]
```

**Process:**

```text
s1 = "ab" + "c" = "abc"
s2 = "a" + "bc" = "abc"

Compare:
"abc" == "abc"
```

**Output:**

```text
True
```

---

## Example 2

**Input:**

```text
word1 = ["a", "cb"]
word2 = ["ab", "c"]
```

**Process:**

```text
s1 = "a" + "cb" = "acb"
s2 = "ab" + "c" = "abc"

Compare:
"acb" != "abc"
```

**Output:**

```text
False
```

---

## Example 3

**Input:**

```text
word1 = ["abc", "d", "defg"]
word2 = ["abcddefg"]
```

**Process:**

```text
s1 = "abc" + "d" + "defg" = "abcddefg"
s2 = "abcddefg"

Compare:
"abcddefg" == "abcddefg"
```

**Output:**

```text
True
```

## Complexity

- **Time Complexity:** `O(n + m)`
- **Space Complexity:** `O(n + m)`