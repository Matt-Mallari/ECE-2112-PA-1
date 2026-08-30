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
#### **Objective:** Create a function named swap_bookends() that accepts a list containing at least two elements, swapping the first and last elements without disrupting the order of the middle elements.

The Following Methods/Functions were used:

```python
def swap_bookends(items: list) -> list:
    if len(items) < 2:
        raise ValueError("List must contain at least two elements.")
```
The function enforces a list input via type hinting. The len() function acts as a safeguard; if a list with fewer than two elements is passed, a ValueError is triggered, preventing unpacking errors later in the execution.

```python
    first, *middle, last = items
```
This utilizes Python's extended sequence unpacking. By placing variables on the left side of the assignment operator, Python binds the first element to first, the final element to last, and uses the asterisk (*) to collect all intermediate elements into a sublist called middle.

```python
   return [last, *middle, first]
```
To complete the swap, a new list is bracketed and returned with last at the beginning and first at the end. The *middle variable is unpacked between them, restoring the inner elements to their exact original positions.

To see the main Python program for Experiment 1, click this link (Insert Link Here), download the .ipynb file, open it in Jupyter Notebook, and run all cells.

### **README File Version History**
* 2026, August 21: File Created
* 2026, August 30: Added link to .pynb file | Segmented code blocks for detailed, line-by-line methodological explanations. Added Jupyter Notebook file link and finalized formatting.
