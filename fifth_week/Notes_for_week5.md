**TA Notes on NumPy Arrays and Slicing**

## **1. Introduction to NumPy**
NumPy (Numerical Python) is a powerful library for numerical computing in Python. It provides support for large, multi-dimensional arrays and matrices along with mathematical functions to operate on them efficiently.

### **Key Features of NumPy:**
- Fast and efficient operations on arrays.
- Support for multi-dimensional arrays (1D, 2D, 3D, etc.).
- Advanced mathematical and statistical functions.
- Broadcasting and vectorized operations for performance optimization.
- Array slicing for accessing and modifying specific elements.

## **2. Creating a 1-D NumPy Array**
A **1-D array** is a simple list-like structure containing elements of the same data type.

```python
import numpy as np
arr = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9])
```

**Reversing the Array Using Negative Slicing:**
```python
print(arr[::-1])
```
This prints the elements in reverse order.

## **3. Array Slicing**
Slicing allows extracting specific portions of an array using `start:stop:step` notation.

### **Basic Slicing Operations on a 1D Array:**
Given `arr = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9])`:
- **Last 3 elements:** `arr[-3:]` → `[7, 8, 9]`
- **First 3 elements:** `arr[:3]` → `[1, 2, 3]`
- **Middle 3 elements:** `arr[3:6]` → `[4, 5, 6]`
- **5th-last to 2nd-last element:** `arr[-5:-1]` → `[5, 6, 7, 8]`
- **Replacing every second element from index 1 with 0:**
  ```python
  arr[1::2] = 0
  print(arr)
  ```
  Output: `[1, 0, 3, 0, 5, 0, 7, 0, 9]`

## **4. Working with 2-D Arrays (Matrices)**
A **2-D NumPy array** is structured as rows and columns, like a matrix.

```python
matrix = np.array([
    [1, 2, 3, 4],
    [5, 6, 7, 8],
    [9, 10, 11, 12],
    [13, 14, 15, 16]
])
```

### **Basic Slicing Operations on a 2D Array:**
- **Last 2 columns:** `matrix[:, -2:]`
- **First 2 rows:** `matrix[:2, :]`
- **Replacing the central 2×2 sub-matrix with its max value:**
  ```python
  central_max = np.max(matrix[1:3, 1:3])
  matrix[1:3, 1:3] = central_max
  print(matrix)
  ```

## **5. Updating One Matrix with Another**
Given two matrices `A` and `B`, we can selectively replace elements in `A` with corresponding elements in `B` using slicing.

```python
A[::2, ::2] = B[::2, ::2]
print(A)
```
This replaces every second element in `A` (starting from index 0 along both rows and columns) with elements from `B`.

## **6. Creating a 3D NumPy Array from a 2D Matrix**
A **3-D array** is a collection of 2D slices. We can extract four 2×2 matrices from a 4×4 matrix and store them in a 3D array.

```python
B = np.array([
    A[:2, :2],  # Top-left
    A[:2, 2:],  # Top-right
    A[2:, :2],  # Bottom-left
    A[2:, 2:]   # Bottom-right
])
```

### **Understanding the Output Format:**
Each **2×2 matrix** is stored as a separate slice in the 3D array.

## **7. Summary**
- NumPy arrays are efficient for numerical operations.
- Slicing allows easy extraction and modification of elements.
- `arr[::-1]` reverses an array.
- Use `array[start:stop:step]` for slicing 1D arrays.
- Use `array[row_start:row_end, col_start:col_end]` for slicing 2D arrays.
- A 3D array can be created by stacking multiple 2D slices.

