# **ECE-2112-PA-1**
**Dean Matthew M. Calibut | 2ECE-D**

This repository breaks down the objectives and provides a detailed, step-by-step discussion for each problem in Experiment 1 (PA-1). This experiment introduces foundational Python programming concepts through three specific string and list manipulation challenges.

# **1. The Word Rotation Problem**
#### **Objective:** Create a function named rotate_word() that accepts a non-empty string. Move the first character of the string to the end while preserving both the original capitalization and the order of the remaining letters.

The Following Methods/Functions were used:

```python
def rotate_word(text: str) -> str:
    if not isinstance(text, str) or not text.strip():
        raise ValueError("Argument must be a non-empty string.")
```
To ensure the function is robust, type hinting (text: str -> str) is used to specify expected inputs and outputs. The isinstance() function verifies the input is strictly a string. Additionally, .strip() evaluates if the user inputted only blank spaces, allowing the function to raise a ValueError for invalid or empty inputs.

```python
if len(text) <= 1:
        return text
```
The len() function identifies the character count. If the string is a single character (or somehow empty despite previous checks), it returns the input immediately to prevent unnecessary processing or slicing errors.

```python
return text[1:] + text[0]
```
This achieves the rotation using Python's string slicing. Since Python uses zero-based indexing, text[0] extracts the initial character, while text[1:] captures the rest of the string from the second character onward. By concatenating these parts, the first character is seamlessly appended to the back. Because this rearranges existing segments rather than altering the characters themselves, the original case is naturally maintained.

# **2. The Username Builder Problem**
#### **Objective:** Create a function named make_username() that processes a first and last name into a standardized username format that is entirely lowercase, contains no spaces, and is separated by a single period.

The Following Methods/Functions were used:

```python
def make_username(first_name: str, last_name: str) -> str:
```
The function is established with type hints requiring two distinct string inputs for the first and last names, explicitly returning a single formatted string.

```python
    clean_first = first_name.lower().replace(" ", "")
    clean_last = last_name.lower().replace(" ", "")
```
To implement this efficiently, two built-in string methods are chained. The .lower() method converts all letters to lowercase. Immediately after, .replace(" ", "") substitutes any space characters with an empty string, effectively stripping out all spaces from multi-word names (e.g., "Mary Jane").

```python
    return clean_first + "." + clean_last
```
Once both names are sanitized, they are concatenated with a literal period (".") in the center to produce and return the final, formatted username string.

# **3. The Bookend Swap Problem**
#### **Objective:** Swap the first and last elements of a list without modifying the original input list or disrupting the order of the middle elements.

This solution utilizes Python's extended sequence unpacking. By assigning the input list to the variables first, *middle, last, Python binds the first element to first, the final element to last, and uses the asterisk (*) to collect all remaining intermediate elements into a sublist called middle. To complete the swap, a new list is constructed with last at the beginning, first at the end, and *middle unpacked between them to restore the inner elements to their exact original positions.

Below is the function constructed:

```python
def swap_bookends(items):
    first, *middle, last = items

    return [last, *middle, first]
```

### **README File Version History**
* 2026, August 21: File Created
* 2026, August 30: Added link to .pynb file | Improved discussion
