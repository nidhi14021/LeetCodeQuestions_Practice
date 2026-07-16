# 2114. Maximum Number of Words Found in Sentences

**Problem Link:** https://leetcode.com/problems/maximum-number-of-words-found-in-sentences/

## Problem
Given an array of strings `sentences`, where each string represents a sentence consisting of words separated by a single space, return the maximum number of words in a single sentence.

## Approach
- Iterate through each sentence in the array.
- Split the sentence into words using `split()`.
- Count the number of words using `len()`.
- Keep track of the maximum word count.

## Solution

```python
class Solution:
    def mostWordsFound(self, sentences: List[str]) -> int:
        max_val = 0

        for sentence in sentences:
            max_val = max(max_val, len(sentence.split()))

        return max_val
```

## Complexity
- **Time Complexity:** `O(n × m)`
  - `n` = number of sentences
  - `m` = average length of a sentence
- **Space Complexity:** `O(m)`
  - Due to the list created by `split()`.