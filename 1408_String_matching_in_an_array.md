# 1408. String Matching in an Array

**Problem Link:** https://leetcode.com/problems/string-matching-in-an-array/

## Problem

Given an array of strings `words`, return all strings that are a **substring of another word** in the array.

## Approach

- Use two loops to compare every word with every other word.
- Make sure we are not comparing a word with itself.
- Check if `words[i]` is present inside `words[j]`.
- If it is present, add it to the result list.
- Use `break` so the same word is added only once.

## Solution

```python
class Solution:
    def stringMatching(self, words: List[str]) -> List[str]:
        arr = []

        for i in range(len(words)):
            for j in range(len(words)):
                if i != j and words[i] in words[j]:
                    arr.append(words[i])
                    break

        return arr
```

## Example 1

**Input:**

```text
words = ["mass", "as", "hero", "superhero"]
```

**Process:**

```text
"as" in "mass" → True
"hero" in "superhero" → True
```

**Output:**

```text
["as", "hero"]
```

## Example 2

**Input:**

```text
words = ["leetcode","et","code"]
```

**Process:**

```text
"et" in "leetcode" → True
"code" in "leetcode" → True
```

**Output:**

```text
["et", "code"]
```

## Complexity

- **Time Complexity:** `O(n² × m)`
- **Space Complexity:** `O(k)`

Where:
- `n` = number of words.
- `m` = average length of the words.
- `k` = number of matching words.