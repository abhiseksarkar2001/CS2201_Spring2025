**# TA Notes on NumPy Arrays and Slicing**

## **Introduction to NumPy**
NumPy (Numerical Python) is a powerful library for numerical computing in Python. It provides support for large, multi-dimensional arrays and matrices along with mathematical functions to operate on them efficiently.

### **Key Features of NumPy:**
- Fast and efficient operations on arrays.
- Support for multi-dimensional arrays (1D, 2D, 3D, etc.).
- Advanced mathematical and statistical functions.
- Broadcasting and vectorized operations for performance optimization.
- Array slicing for accessing and modifying specific elements.

## **Question 1: Reverse a 1D Array**
### **Problem Statement:**
Create a 1-D NumPy array containing 9 elements, taken as inputs from the user. Use a single statement and negative slicing to print the array elements in reverse order.

### **Solution:**
```python
import numpy as np
arr = np.array([int(input(f"Enter element {i+1}: ")) for i in range(9)])
print(arr[::-1])
```
### **Explanation:**
- `np.array([...])` creates a NumPy array from user inputs.
- `[::-1]` reverses the array using negative slicing.

## **Question 2: Array Slicing Operations**
### **Problem Statement:**
Given a 1D NumPy array of 9 elements, extract specific portions using slicing:
- Last 3 elements
- First 3 elements
- Middle 3 elements
- 5th-last to 2nd-last elements using negative slicing
- Replace every second element (starting from index 1) with 0

### **Solution:**
```python
print("Last 3 elements:", arr[-3:])
print("First 3 elements:", arr[:3])
print("Middle 3 elements:", arr[3:6])
print("5th-last to 2nd-last:", arr[-5:-1])
arr[1::2] = 0
print("Updated array:", arr)
```
### **Explanation:**
- `arr[-3:]` selects the last 3 elements.
- `arr[:3]` selects the first 3 elements.
- `arr[3:6]` selects the middle 3 elements.
- `arr[-5:-1]` selects from the 5th-last to the 2nd-last element.
- `arr[1::2] = 0` replaces every second element from index 1 with `0`.

## **Question 3: Slicing a 2D Matrix**
### **Problem Statement:**
Given a 4×4 matrix, extract:
- Last 2 columns
- First 2 rows
- Replace the central 2×2 sub-matrix with its maximum value.

### **Solution:**
```python
matrix = np.array([...])  # 4x4 matrix
print("Last 2 columns:\n", matrix[:, -2:])
print("First 2 rows:\n", matrix[:2, :])
central_max = np.max(matrix[1:3, 1:3])
matrix[1:3, 1:3] = central_max
print("Updated matrix:\n", matrix)
```
### **Explanation:**
- `matrix[:, -2:]` extracts the last two columns.
- `matrix[:2, :]` extracts the first two rows.
- `np.max(matrix[1:3, 1:3])` finds the max value in the central sub-matrix.
- `matrix[1:3, 1:3] = central_max` updates that sub-matrix with the max value.

## **Question 4: Updating Matrix A with B**
### **Problem Statement:**
Replace every second element (starting from index 0 along rows and columns) in matrix A with the corresponding element in matrix B.

### **Solution:**
```python
A[::2, ::2] = B[::2, ::2]
print("Updated matrix A:\n", A)
```
### **Explanation:**
- `A[::2, ::2]` selects every alternate element in A (starting at 0,0) and replaces it with elements from B.

## **Question 5: Creating a 3D Array from a 2D Matrix**
### **Problem Statement:**
Given a 4×4 matrix, create a 3D NumPy array (4×2×2) composed of its four 2×2 corner sub-matrices.

### **Solution:**
```python
B = np.array([
    A[:2, :2],  # Top-left
    A[:2, 2:],  # Top-right
    A[2:, :2],  # Bottom-left
    A[2:, 2:]   # Bottom-right
])
print("Array B:")
for block in B:
    print(block, "\n")
```
### **Explanation:**
- `A[:2, :2]` selects the top-left 2×2 sub-matrix.
- `A[:2, 2:]` selects the top-right 2×2 sub-matrix.
- `A[2:, :2]` selects the bottom-left 2×2 sub-matrix.
- `A[2:, 2:]` selects the bottom-right 2×2 sub-matrix.
- These matrices are combined into a 3D array `B`.

## **Summary**
- NumPy arrays are efficient for numerical operations.
- Slicing allows easy extraction and modification of elements.
- `[::-1]` reverses an array.
- `array[start:stop:step]` slices a 1D array.
- `array[row_start:row_end, col_start:col_end]` slices a 2D array.
- A 3D array can be created by stacking multiple 2D slices.
