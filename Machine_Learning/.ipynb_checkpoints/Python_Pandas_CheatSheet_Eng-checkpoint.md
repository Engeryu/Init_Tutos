# Python and Pandas lexic
**Author:** Gaspard-Fauvelle Angel  
**License:** [CC BY-NC-SA 2.0](https://creativecommons.org/licenses/by-nc-sa/2.0/)  

Voici la version française du document [Python & Pandas CheatSheet](./Python_Pandas_CheatSheet_FR.md)

---

## Table of Contents
- [I. Introduction to Data Types and Variables](#I.-Introduction-to-Data-Types-and-Variables)
- [1.2. Data types (Scalar types)](#1.2.-Data-types-(Scalar-types))
- [Ⅱ. Built-in Functions Python](#Ⅱ.-Built-in-Functions-Python)
- [III. Concatenation, Arithmetic operations & Comparisons](#III.-Concatenation,-Arithmetic-operations-&-Comparisons)
- [3.1. Concatenations](#3.1.-Concatenations)
- [Ⅳ. Introduction to Data Structures (Abstract data types)](#Ⅳ.-Introduction-to-Data-Structures-(Abstract-data-types))
- [4.1. Sequences and Collection Data Structures (Vector/2-Dimensional Data Types)](#4.1.-Sequences-and-Collection-Data-Structures-(Vector/2-Dimensional-Data-Types))
- [4.2. Difference between Python built-in list[] and Numpy built-in array([])](#4.2.-Difference-between-Python-built-in-list[]-and-Numpy-built-in-array([]))

---

## I. Introduction to Data Types and Variables  
### 1.2. Data types (Scalar types)

| **Category**     | **Type**                         | **Description**                                                       | **Examples**                                 |
|------------------|----------------------------------|-----------------------------------------------------------------------|----------------------------------------------|
| Numeric Types    | `int` (Integer Numbers)          | Signed integer of arbitrary precision.                                | `42`, `-7`, `0`, `123456789`, `-999`         |
|                  | `float` (Decimal Numbers)        | Double‑precision floating‑point number.                               | `3.14`, `-0.001`, `0.0`, `2.71828`, `-300.0` |
|                  | `complex` (Imaginary Numbers)    | Complex number of two floats (real and imaginary parts).             | `1+2j`, `-3+4j`, `0+0j`, `3-1j`, `-2+5j`      |
| Boolean Type     | `bool` (Booleans)                | Boolean (a subtype of `int`: `True` == 1, `False` == 0).              | `True`, `False`                              |
| Special Type     | `NoneType`                       | Type of the special value `None`, representing no value.             | `None`                                       |
| Sequence Type    | `str` (Strings)                  | Unicode character string of variable length.                         | `"Bonjour"`, `"Python 3.10"`, `"30"`, `"Hello, world!"`, `"Café"` |
|                  | `object`, `category`             | Pandas‑specific types: `object` for mixed types, `category` for categorical data. | mixed values, categorical codes |

_Primitive data types are the basic building blocks of a programming language:_  
- They are the smallest pieces of information you can use to build more complex constructs in your code.  
- They cannot be broken down into smaller parts.

_These types provide the essential ingredients to perform calculations, store text, make decisions, and more. Everything more complex in your program is built from these basic pieces._

> In Jupyter, press **Shift + Enter** to execute a cell.

---

## Ⅱ. Built-in Functions Python

| **Category**  | **Function** | **Description**                                             | **Examples**                            |
|---------------|--------------|-------------------------------------------------------------|-----------------------------------------|
| **Returns**   | `len()`      | Returns the length of an object (list, string, etc.).       | `len([1, 2, 3])` returns `3`            |
|               | `type()`     | Returns the type of the given object.                       | `type(42)` returns `<class 'int'>`      |
|               | `sum()`      | Returns the sum of an iterable of numbers.                  | `sum([1, 2, 3])` returns `6`            |
|               | `min()`      | Returns the smallest element of an iterable.                | `min([1, 2, 3])` returns `1`            |
|               | `max()`      | Returns the largest element of an iterable.                 | `max([1, 2, 3])` returns `3`            |
|               | `abs()`      | Returns the absolute value of a number.                     | `abs(-7)` returns `7`                   |
|               | `round()`    | Rounds a float to the specified number of decimal places.   | `round(3.14159, 2)` returns `3.14`      |
|               | `sorted()`   | Returns a new sorted list from the given iterable.          | `sorted([3, 1, 2])` returns `[1, 2, 3]` |
| **Creates**   | `range()`    | Generates a sequence of integers (for `for` loops).        | `range(5)` → `[0, 1, 2, 3, 4]`           |
|               | `list()`     | Creates/converts a list from an iterable.                   | `list("abc")` returns `['a','b','c']`   |
|               | `set()`      | Creates/converts a set from an iterable, removing duplicates.| `set([1,2,2,3])` returns `{1,2,3}`      |
|               | `dict()`     | Creates/converts a dict from an iterable of key–value pairs.| `dict([("a",1),("b",2)])` returns `{'a':1,'b':2}` |
|               | `zip()`      | Combines iterables element‑wise into tuples.                | `zip([1,2,3],["a","b","c"])` → `[(1,'a'),(2,'b'),(3,'c')]` |
| **Converts**  | `str()`      | Converts an object to a string.                             | `str(42)` returns `"42"`               |
|               | `int()`      | Converts a string or float to an integer.                   | `int("42")` returns `42`               |
|               | `float()`    | Converts a string or integer to a float.                    | `float("3.14")` returns `3.14`         |
| **Others**    | `print()`    | Displays messages on the screen or console.                 | `print("Hello")` outputs `Hello`       |
|               | `input()`    | Reads a line of text from standard input (keyboard).        | `name = input("Enter name: ")`         |

_Python’s built‑in functions let you perform common tasks without importing extra libraries._  
_Learn more: [Complete list of built‑ins](https://docs.python.org/3/library/functions.html)._

---

## III. Concatenation, Arithmetic operations & Comparisons

| **Category**             | **Operator**      | **Symbol** | **Description**                                      | **Example** | **Breakdown**           | **Result** |
|--------------------------|-------------------|------------|------------------------------------------------------|-------------|-------------------------|------------|
| Arithmetic Operations    | Addition          | `+`        | Adds two numbers.                                    | `5 + 3`     | `5 + 3`                 | `8`        |
|                          | Subtraction       | `-`        | Subtracts one number from another.                   | `5 - 3`     | `5 - 3`                 | `2`        |
|                          | Multiplication    | `*`        | Multiplies two numbers.                              | `3 * 5`     | `5 + 5 + 5`             | `15`       |
|                          | Division          | `/`        | Divides one number by another.                       | `6 / 3`     | `6 ÷ 3 = 2`             | `2.0`      |
|                          | Floor Division    | `//`       | Integer quotient of the division.                    | `7 // 3`    | `7 ÷ 3 = 2`             | `2`        |
|                          | Modulus           | `%`        | Remainder of the division.                           | `7 % 3`     | `7 - (3 * 2) = 1`       | `1`        |
|                          | Exponentiation    | `**`       | Raises a number to the power of another.             | `2 ** 3`    | `2 * 2 * 2 = 8`         | `8`        |
| Comparison Operators     | Equal to          | `==`       | Checks equality.                                     | `5 == 5`    | Is 5 equal to 5?        | `True`     |
|                          | Not equal to      | `!=`       | Checks inequality.                                   | `5 != 3`    | Is 5 ≠ 3?               | `True`     |
|                          | Greater than      | `>`        | Checks if left operand is greater.                   | `5 > 3`     | Is 5 > 3?               | `True`     |
|                          | Less than         | `<`        | Checks if left operand is smaller.                   | `3 < 5`     | Is 3 < 5?               | `True`     |
|                          | ≥ (Greater or eq) | `>=`       | Checks ≥ relationship.                               | `5 >= 5`    | Is 5 ≥ 5?               | `True`     |
|                          | ≤ (Less or eq)    | `<=`       | Checks ≤ relationship.                               | `3 <= 5`    | Is 3 ≤ 5?               | `True`     |
|                          | Identity is       | `is`       | Checks if both refer to same object.                 | `a is b`    | Same object in memory?  | `True/False`|
|                          | Identity is not   | `is not`   | Checks if different objects.                         | `a is not b`| Different object?       | `True/False`|
|                          | In                | `in`       | Checks membership in a sequence.                     | `'a' in 'apple'`  | `'a'` in `"apple"`? | `True`     |
|                          | Not in            | `not in`   | Checks absence in a sequence.                       | `'b' not in 'apple'`| `'b'` not in `"apple"`?| `True`     |
| Logical Operations       | AND               | `and`      | Returns `True` if both are `True`.                  | `True and False`| Both true?         | `False`    |
|                          | OR                | `or`       | Returns `True` if at least one is `True`.           | `True or False`| One true?          | `True`     |
|                          | NOT               | `not`      | Returns `True` if operand is `False`.                | `not True`    | Not true?           | `False`    |
|                          | NAND              | `not (a and b)` | `True` if not both are `True`.                | `not (True and False)`| Not both true?| `True`     |
|                          | NOR               | `not (a or b)`  | `True` if neither is `True`.                   | `not (True or False)`| Neither true?  | `False`    |
|                          | XOR               | `a != b`   | `True` if operands differ.                          | `True != False`| Are different?     | `True`     |
|                          | XNOR              | `not (a != b)`| `True` if operands are same.                     | `not (True != False)`| Are same?      | `False`    |

#### 3.1. Concatenations

Concatenation joins two or more strings end‑to‑end into a single string. In Python, use the `+` operator:

```python
variable1 = "Salut"
variable2 = "Comment allez‑vous ?"
print(variable1 + ' ' + variable2)  # Salut Comment allez‑vous ?
print(variable2 + ' ' + variable1)  # Comment allez‑vous ? Salut
```

---

## Ⅳ. Introduction to Data Structures (Abstract data types)

### 4.1. Sequences and Collection Data Structures (Vector/2-Dimensional Data Types)

There are other things we can store as variables, vector/uni-dimensional variables:

| **Category**   | **Data Structure** | **Description**                                                                                                      | **Examples**                                                        |
|----------------|--------------------|----------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------|
| Sequence       | list             | Ordered, mutable sequence that can contain elements of various types.                                                | [1, 2, 3], ["apple", "banana", "cherry"], [42, "hello", True] |
|                | tuple            | Ordered, immutable sequence used to group elements that should not be modified.                                      | (1, 2, 3), ("red", "green", "blue"), ("a", 42, False)         |
|                | range            | Immutable sequence representing an arithmetic progression, often used in loops for iteration.                        | range(5), range(1, 10), range(0, 20, 2)                       |
| Collection     | set              | Unordered, mutable collection of unique elements.                                                                    | {1, 2, 3}, {"cat", "dog", "bird"}, {10, 20, 30}               |
|                | frozenset        | Immutable version of a set, ideal for situations where a collection of unique elements must remain unchanged.        | frozenset({1, 2, 3}), frozenset({"a", "b", "c"})                |
| Dictionary     | dict             | Collection of key-value pairs with unique keys. In recent Python versions, insertion order is preserved.             | {"name": "Alice", "age": 30}, {1: "one", 2: "two", 3: "three"}  |

| **Feature**                 | **Sequences**                 | **Collections**                  | **Dictionaries**                       |
|-----------------------------|-------------------------------|----------------------------------|----------------------------------------|
| Ordered                     | ✔ (list, tuple, range) | ✖ (Unordered set, frozenset) | ✔ (Ordered since Python 3.7)          |
| Mutable                     | ✔ (list, array)          | ✔ (set)                        | ✔ (dict)                            |
| Immutable                   | ✔ (tuple, range)         | ✔ (frozenset)                  | ✖                                     |
| Allows duplicates           | ✔                            | ✖ (set, frozenset)           | ✖ (Keys unique, values can duplicate) |
| Key-Value pairs             | ✖                            | ✖                                | ✔                                     |
| Holds heterogeneous types   | ✔ (list, tuple)          | ✔ (set)                        | ✔ (dict)                            |
| Homogeneous types only      | ✔ (array)                  | ✖                                | ✖                                     |
| Fast membership testing     | ✖                            | ✔ (set, frozenset)           | ✔                                     |
| Iteration supported         | ✔                            | ✔                                | ✔                                     |
| Indexing supported          | ✔ (list, tuple, range) | ✖                                | ✔ (via keys)                          |

### **Additional Explanations**:
- **Ordered**: list, tuple, and range have a defined order, as do dict since Python 3.7, whereas set and frozenset do not have an order.
- **Mutable vs Immutable**: list and dict allow you to modify their elements, unlike tuple, range, and frozenset, which are immutable.
- **Duplicates**: set, frozenset, and the keys of dict do not allow duplicates, which ensures uniqueness.
- **Key-Value pairs**: A feature unique to dict.
- **Homogeneous types**: Required in array (strictly defined types, e.g., all int or all float).
- **Membership testing**: set and frozenset are optimized for testing whether an element belongs to the collection, as are dict (via keys).

[🔗 Lists/Arrays methods](https://www.w3schools.com/python/python_ref_list.asp) | [🔗 Tuples methods](https://www.w3schools.com/python/python_ref_tuple.asp) |
[🔗 Ensembles methods](https://www.w3schools.com/python/python_ref_set.asp) | [🔗 Dictionaries methods](https://www.w3schools.com/python/python_ref_dictionary.asp) | [🔗 Python keywords](https://www.w3schools.com/python/python_ref_keywords.asp)

### **4.2. Difference between Python built-in list[] and Numpy built-in array([])**

| **Feature**           | **Array**                                                                                      | **List**                                                              |
|-----------------------|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------|
| **Element Type**      | Must contain only elements of the same type.                                                   | Can contain elements of different types (int, str, etc.).             |
| **Performance**       | More compact and faster for operations on homogeneous types (integers, floats, etc.).          | More general-purpose but slightly less performant.                    |
| **Compatibility**     | Requires the array module to use.                                                               | Built-in type, always available.                                       |
| **Example**           | array('i', [1, 2, 3]) (only integers).                                                         | [1, "a", 3.5, True] (elements of mixed types).                        |

---

**You can now redirect to [NumPy/Pandas](./NumPy_Pandas_Eng.md) CheatSheet**

_Edited: 2025/04/22_