# 📝 Week 6 - Notes:

## 📌 Q1: Creating a Dictionary from a List  

### **Concept:**  
- The input is a list containing alternating names and ages.  
- We need to form key-value pairs using consecutive elements.  

### **Key Steps:**  
1. **Take input as a comma-separated string and split it into a list.**  
   ```python
   input_list = input("Enter names and ages: ").split(',')
   ```
   - `.split(',')` separates values into a list based on commas.  

2. **Remove extra whitespace using list comprehension.**  
   ```python
   input_list = [item.strip() for item in input_list]
   ```
   - `.strip()` removes unnecessary spaces.  

3. **Use dictionary comprehension to create key-value pairs.**  
   ```python
   name_age_dict = {input_list[i]: input_list[i+1] for i in range(0, len(input_list), 2)}
   ```
   - `range(0, len(input_list), 2)` ensures we pick pairs correctly.  

---

## 📌 Q2: Creating a List of Tuples  

### **Concept:**  
- Similar to Q1, but store the values as **tuples** instead of a dictionary.  

### **Key Steps:**  
1. **Process input and strip whitespace (same as Q1).**  
2. **Use list comprehension to form tuples.**  
   ```python
   tuple_list = [(input_list[i], input_list[i+1]) for i in range(0, len(input_list), 2)]
   ```
   - This pairs elements as tuples: `[(name, age), (name, age), ...]`.  

---

## 📌 Q3: Solving a System of Linear Equations  

### **Concept:**  
- Use `numpy.linalg.solve()` to find the intersection of three planes.  
- Check if the coefficient matrix is singular using `np.linalg.det()`.  

### **Key Steps:**  
1. **Define the coefficient matrix and RHS constants.**  
   ```python
   A = np.array([[1, 2, 3], [4, 8, 66], [7, 81, 9]])
   b = np.array([2, 3, 4])
   ```
2. **Check if the determinant is near zero (singular matrix).**  
   ```python
   det_A = np.linalg.det(A)
   if abs(det_A) < 0.00001:
       print("Matrix is singular, no unique solution.")
   ```
3. **Solve the system using `np.linalg.solve()`.**  
   ```python
   solution = np.linalg.solve(A, b)
   ```

---

## 📌 Q4: Decimal to Binary Conversion  

### **Concept:**  
- Convert a **decimal number to binary** using `bin(n)[2:]`.  
- Apply this function element-wise on a `numpy` array using `np.vectorize()`.  

### **Key Steps:**  
1. **Define the conversion function.**  
   ```python
   def d2b(n):
       return int(bin(n)[2:])  # Convert binary string to integer
   ```
2. **Use `np.vectorize()` to apply on an array.**  
   ```python
   numpy_DecimalToBinary = np.vectorize(d2b)
   ```

---

## 📌 Q5: Summing Rows and Columns in a 2D Array  

### **Concept:**  
- Use `numpy.sum()` to sum **rows (students)** and **columns (subjects)**.  
- Reshape for **1D and 2D outputs**.  

### **Key Steps:**  
1. **Row-wise (Student-wise) Sum:**  
   ```python
   student_sums = np.sum(marks, axis=1)  # 1D
   student_sums_2D = student_sums.reshape(-1, 1)  # Convert to column vector
   ```
2. **Column-wise (Subject-wise) Sum:**  
   ```python
   subject_sums = np.sum(marks, axis=0)  # 1D
   subject_sums_2D = subject_sums.reshape(1, -1)  # Convert to row vector
   ```

---

## 📌 Q6: Removing Elements from a Numpy Array  

### **Concept:**  
- Use `np.setdiff1d(A, B)` to remove elements in `B` from `A`.  

### **Key Steps:**  
```python
C = np.setdiff1d(A, B)
```
- `np.setdiff1d()` returns elements in `A` that are **not** in `B`.  

---

## 📌 Q7: Difference Between `np.multiply()` and `np.matmul()`  

### **Concept:**  
- `np.multiply()` performs **element-wise multiplication**.  
- `np.matmul()` performs **matrix multiplication** (dot product).  

### **Key Steps:**  
1. **Element-wise multiplication:**  
   ```python
   np.multiply(arr1, arr2)  # Multiplies corresponding elements
   ```
2. **Matrix multiplication:**  
   ```python
   np.matmul(arr1, arr2)  # Computes the dot product
   ```

---

## 📌 Q8: Applying a Function on a List and a NumPy Array  

### **Concept:**  
- Apply `f(x) = x³ + 1` on both **Python lists** and **NumPy arrays**.  

### **Key Steps:**  
1. **Python list approach:**  
   ```python
   Lout = [f(x) for x in L]
   ```
2. **NumPy array approach:**  
   ```python
   Aout = f(A)  # Vectorized operation
   ```

---

## 📌 Q9: Applying a Function Using `frompyfunc()` and `vectorize()`  

### **Concept:**  
- Define a function `f(x)` with conditional logic.  
- Use `np.frompyfunc()` and `np.vectorize()` to apply it element-wise.  

### **Key Steps:**  
1. **Define `f(x)`:**  
   ```python
   def f(x):
       if x < 0:
           return 0
       elif x == 0:
           return 1
       else:
           return x % 3
   ```
2. **Using `np.frompyfunc()`:**  
   ```python
   f_frompyfunc = np.frompyfunc(f, 1, 1)  # 1 input, 1 output
   ```
3. **Using `np.vectorize()`:**  
   ```python
   f_vectorized = np.vectorize(f)
   ```

---

## 📌 Q10: Using `np.linspace()` for Equally Spaced Points  

### **Concept:**  
- Generate **10 equally spaced points** between `20` and `21`.  
- Explore behavior with `endpoint=True` and `endpoint=False`.  

### **Key Steps:**  
1. **Including the endpoint (`21` is part of the list):**  
   ```python
   np.linspace(20, 21, num=10, endpoint=True)
   ```
2. **Excluding the endpoint (`21` is not included):**  
   ```python
   np.linspace(20, 21, num=10, endpoint=False)
   ```
3. **Find interval length:**  
   ```python
   interval_length = points_inclusive[1] - points_inclusive[0]
   ```

---

## 🎯 Summary  

| **Concept**            | **Key Function**              |
|------------------------|-----------------------------|
| Dictionary from List   | `{list[i]: list[i+1]}`      |
| Tuples from List       | `[(list[i], list[i+1])]`    |
| Solve Linear Equations | `np.linalg.solve(A, b)`     |
| Decimal to Binary      | `np.vectorize(bin(n)[2:])`  |
| Sum Rows/Columns      | `np.sum(A, axis=0/1)`       |
| Remove Elements        | `np.setdiff1d(A, B)`        |
| Element-wise vs MatMul | `np.multiply() vs np.matmul()` |
| Function Application   | `np.frompyfunc(), np.vectorize()` |
| Linspace Usage         | `np.linspace(start, end, num, endpoint)` |

---
