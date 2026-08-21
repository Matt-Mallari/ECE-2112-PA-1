# **ECE-2112-PA-1**
**Dean Matthew M. Calibut | 2ECE-D**

This repository breaks down the objectives and provides a detailed discussion for each problem in Experiment 1 (PA-1).

# **1. The Word Rotation Problem**
#### **Objective:** Move the first character of a string to the end while preserving both the original capitalization and the order of the remaining letters.

This is achieved using Python's string slicing and indexing. Since Python uses zero-based indexing, text[0] extracts the initial character, while text[1:] captures the rest of the string from the second character onward. By concatenating these two parts (text[1:] + text[0]), the first character is seamlessly appended to the back. Because this approach simply rearranges existing segments rather than altering the characters themselves, the original case is naturally maintained.

Below is the function constructed:

```
# def rotate_word(text):
    return text[1:] + text[0]
```
