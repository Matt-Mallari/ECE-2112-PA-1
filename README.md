# **ECE-2112-PA-1**
**Dean Matthew M. Calibut | 2ECE-D**

This repository breaks down the objectives and provides a detailed discussion for each problem in Experiment 1 (PA-1).

# **1. The Word Rotation Problem**
#### **Objective:** Move the first character of a string to the end while preserving both the original capitalization and the order of the remaining letters.

This is achieved using Python's string slicing and indexing. Since Python uses zero-based indexing, text[0] extracts the initial character, while text[1:] captures the rest of the string from the second character onward. By concatenating these two parts (text[1:] + text[0]), the first character is seamlessly appended to the back. Because this approach simply rearranges existing segments rather than altering the characters themselves, the original case is naturally maintained.

Below is the function constructed:

```python
def rotate_word(text):
    return text[1:] + text[0]
```

# **2. The Username Builder Problem**
#### **Objective:** Process a first and last name into a standardized username format that is entirely lowercase, contains no spaces, and is separated by a single period.

To implement this efficiently, we chain two built-in string methods together. The .lower() method converts all letters to lowercase, while .replace(" ", "") substitutes any space characters with an empty string to remove them entirely. Once both names are sanitized, they are concatenated with a literal period (".") in the center to produce the final, formatted username string.

Below is the function constructed:

```python
def make_username(first_name, last_name):
    clean_first = first_name.lower().replace(" ","")
    clean_last = last_name.lower().replace(" " , "")
    return clean_first + "." + clean_last
```

# **3. The Bookend Swap Problem**
#### **Objective:** Swap the first and last elements of a list without modifying the original input list or disrupting the order of the middle elements.

This solution utilizes Python's extended sequence unpacking. By assigning the input list to the variables first, *middle, last, Python binds the first element to first, the final element to last, and uses the asterisk (*) to collect all remaining intermediate elements into a sublist called middle. To complete the swap, a new list is constructed with last at the beginning, first at the end, and *middle unpacked between them to restore the inner elements to their exact original positions.

Below is the function constructed:

```python
def swap_bookends(items):
    first, *middle, last = items

    return [last, *middle, first]
```

### **File Version History**
* 2026, August 21: File Created
