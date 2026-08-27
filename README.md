# ECE2112_PA1
**Made by: Psalm I. Tabat | 2ECE-C**

This repository contains my submission for Programming Assignment No. 1 of "Advanced Computer Programming and Algorithms" for A.Y. 2026-2027. It covers three Python exercises from Module 1 - Base Computing with Python.

# **A. Word Rotation Problem**
Write a function that takes a non-empty string, shifts its first character to the end, and keeps the rest of the characters in order while preserving their original capitalization.

Method used:
- **String slicing** - lets you pull out part of a string using a start and end index. `text[1:]` returns everything after the first character, and `text[0]` isolates the first character.

Example: `"Python"[1:]` --> `"ython"`, and `"Python"[0]` --> `"P"`

The function simply adds these two pieces back together in reverse order:
```python
#defining a function rotate_word() with a parameter 'text'
def rotate_word(text):
    #moves the first character to the end
    return text[1:]+text[0]
 
print(rotate_word("Python"))
print(rotate_word("logic"))
print(rotate_word("Code"))
print(rotate_word("A"))
```
Output:
```
ythonP
ogicl
odeC
A
```

# **B. Username Builder Problem**
This function takes a first name and last name and turns them into a lowercase username, removes any spaces and joining the two names with a period.

Methods used:
- **`.lower()`** - converts every character in a string to lowercase.

Example: `"Ana Maria".lower()` --> `"ana maria"`

- **`.replace()`** - swaps out the spaces with an empty string.

Example: `"ana maria".replace(" ", "")` --> `"anamaria"`

Both methods are applied to first and last name and the cleaned-up results are then joined with a period through concatenation:
```python
#defining a function make_username() with two parameters, 'first_name' and 'last_name'
def make_username(first_name, last_name):
    #making first and last name lowercase, and remove spaces
    first = first_name.lower().replace(" ", "")
    last = last_name.lower().replace(" ", "")
    #concatenate first name, a period, and last name into one string
    return first + "." + last
 
print(make_username("Ada", "Lovelace"))
print(make_username("Alan", "Turing"))
print(make_username("Ana Maria", "De Leon"))
```
Output:
```
ada.lovelace
alan.turing
anamaria.deleon
```
# **C. Bookend Swap Problem**
This function takes a list of at least two items, splits it into its first element, its middle elements, and its last element, then returns a new list with the first and last positions swapped.

Technique used:
- **Unpacking list** - splits a list into separate variables while gathering the leftover elements into their own list using the `*` operator.

Example: `first, *middle, last = [1, 2, 3, 4, 5, 6]` --> `first = 1`, `middle = [2, 3, 4, 5]`, `last = 6`

After unpacking, a new list is assembled by putting `last` at the front, `middle` in the center untouched, and `first` at the end:

```python
#defining a function swap_bookends() with a parameter 'items'
def swap_bookends(items):
    #unpacking the list
    first, *middle, last = items
    #returning and making a new list
    return [last] + middle + [first]
 
#printing a series of lists
print(swap_bookends([1, 2, 3, 4, 5, 6]))
print(swap_bookends(["red", "green", "blue"]))
print(swap_bookends([8, 3]))
```
Output:
```
[6, 2, 3, 4, 5, 1]
['blue', 'green', 'red']
[3, 8]
```

#### **README file Version History:**
August 27, 2026 - Initial README output uploaded.
