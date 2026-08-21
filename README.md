# **ECE-2112-PA-1**
**Dean Matthew M. Calibut | 2ECE-D**

This repository breaks down the objectives and provides a detailed discussion for each problem in Experiment 1 (PA-1).

# **1. The Word Rotation Problem**
#### **Objective:** Move the first character of a string to the end while preserving both the original capitalization and the order of the remaining letters.

This is achieved using Python's string slicing and indexing. Since Python uses zero-based indexing, text[0] extracts the initial character, while text[1:] captures the rest of the string from the second character onward. By concatenating these two parts (text[1:] + text[0]), the first character is seamlessly appended to the back. Because this approach simply rearranges existing segments rather than altering the characters themselves, the original case is naturally maintained.

Below is the function constructed:

```
def rotate_word(text):
    return text[1:] + text[0]
```

# **2. The Username Builder Problem**
#### **Objective:** Process a first and last name into a standardized username format that is entirely lowercase, contains no spaces, and is separated by a single period.

To implement this efficiently, we chain two built-in string methods together. The .lower() method converts all letters to lowercase, while .replace(" ", "") substitutes any space characters with an empty string to remove them entirely. Once both names are sanitized, they are concatenated with a literal period (".") in the center to produce the final, formatted username string.

Below is the function constructed:

```
def make_username(first_name, last_name):
    clean_first = first_name.lower().replace(" ","")
    clean_last = last_name.lower().replace(" " , "")
    return clean_first + "." + clean_last
```
