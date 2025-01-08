# CS2201 Spring 2025 - Week 1 Notes

## General Concepts

### 1. **Lists**
- A list in Python is a collection of elements, which can be of different data types.
- Lists are mutable, meaning you can change their content after creation.
- Common operations:
  - **Create a list:** `x = [1, 2, 3]` or `x = list(range(0, 10))`
  - **Access elements:** `x[0]` (first element), `x[-1]` (last element)
  - **Slicing:** `x[start:end:step]`
  - **Append:** `x.append(value)`
  - **Extend:** `x.extend([4, 5, 6])`
  - **Concatenate:** `x + y`

### 2. **Strings**
- Strings are sequences of characters and are immutable.
- Common string methods:
  - **Find substring:** `x.find("substring")`
  - **Check substring:** `"substring" in x`
  - **Reverse string:** `x[::-1]`
  - **Length:** `len(x)`
  - **Concatenate:** `x + y`

### 3. **Basic Input/Output**
- `input()` is used for input, and `print()` for output.
- Casting inputs to specific types: `int(input("Enter a number: "))`.

### 4. **Functions**
- Define reusable code blocks using `def`.
- Example:
  ```python
  def example_function(param):
      return param * 2


---
## Cheat Sheet

### List Operations
1. **Reverse a List**
   ```python
   x = [1, 2, 3]
   print(x[::-1])  # Output: [3, 2, 1]
   ```
2. **Odd/Even Elements**
   ```python
   odd_elements = x[1::2]  # Odd-indexed elements
   even_elements = x[::2]  # Even-indexed elements
   ```
3. **Concatenate Lists**
   ```python
   combined = x + y
   ```

### String Operations
1. **Reverse a String**
   ```python
   x = "hello"
   print(x[::-1])  # Output: "olleh"
   ```
2. **Find Substring**
   ```python
   if "fox" in x:
       print("Substring exists!")
   ```
3. **Character Slicing**
   ```python
   every_third = x[::3]
   ```

### Miscellaneous
1. **Print a Sentence**
   ```python
   print("It's good to learn Python")
   ```
2. **Data Type Identification**
   ```python
   value = 42
   print(type(value))  # Output: <class 'int'>
   ```

---

## Week 1 Assignments

### Q1. Lists
- **Tasks**: 
  - Create lists, reverse, find max/min, etc.
  - Code examples:
    ```python
    x = list(range(10))  # [0, 1, ..., 9]
    y = list(range(3, 13))  # [3, 4, ..., 12]
    print(x[::-1])  # Reverse list
    print(x.index(7))  # Find index of 7
    ```

### Q2. Strings
- **Tasks**:
  - Substring operations, slicing, reversing.
  - Code examples:
    ```python
    x = "The quick brown fox jumps over the lazy dog"
    print(x[::-1])  # Reverse
    print("fox" in x)  # Check substring
    ```

### Q3. Miscellaneous
- **Tasks**:
  - Print statements, input/output, data types.
  - Code examples:
    ```python
    name = "Abhisek"
    print(f"My name is {name}")
    ```

---

## Tips for Assignments
1. **Test your code**: Use small examples to verify correctness.
2. **Understand slicing**: Practice different slice parameters.
3. **Use Python's built-in methods**: Like `index()`, `len()`, etc.
4. **Read error messages carefully**: They help debug faster.

---

Happy Learning! 😊
