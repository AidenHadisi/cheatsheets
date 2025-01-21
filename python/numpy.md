# 🐍 NumPy Cheatsheet

## 📌 1. Installation & Import

```python
pip install numpy  # Install NumPy
import numpy as np  # Import NumPy
```

---

## 🔹 2. Creating Arrays

```python
a = np.array([1, 2, 3])  # 1D array
b = np.array([[1, 2], [3, 4]])  # 2D array
c = np.zeros((2, 3))  # 2x3 matrix of zeros
d = np.ones((3, 3))  # 3x3 matrix of ones
e = np.eye(3)  # Identity matrix (3x3)
f = np.full((2, 2), 7)  # 2x2 matrix filled with 7
g = np.arange(0, 10, 2)  # [0, 2, 4, 6, 8]
h = np.linspace(0, 1, 5)  # 5 values from 0 to 1. i.e. [0.   0.25 0.5  0.75 1. ]
i = np.random.rand(2, 2)  # 2x2 matrix with random values
k = np.empty((2, 2))  # 2x2 matrix with uninitialized values
j = np.identity(3)  # Identity matrix (3x3)
```

Random Arrays:

```python
np.random.rand(3,3)    # Uniform distribution
np.random.randn(3,3)   # Standard normal distribution
np.random.randint(1,10, (3,3))  # Random integers
np.random.choice([1, 2, 3, 4])  # Random choice from array
```

---

## 🔹 3. Array Attributes

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
print(arr.shape)  # (2, 3) - dimensions
print(arr.ndim)  # 2 - number of dimensions
print(arr.size)  # 6 - total elements
print(arr.dtype)  # int64 (depends on system)
```

---

## 🔹 4. Indexing & Slicing

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])

print(arr[0, 1])  # 2 (row 0, col 1)
print(arr[:, 1])  # [2, 5] (all rows, col 1)
print(arr[1, :])  # [4, 5, 6] (row 1, all cols)
print(arr[0, 1:3])  # [2, 3] (row 0, cols 1 to 2)
```

---

## 🔹 5. Reshaping & Transposing

```python
arr.reshape(2,2)  # Change shape
arr.flatten()  # Convert to 1D
arr.ravel()  # Another way to flatten
arr.T  # Transpose
```

---

## 🔹 6. Array Operations

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(a + b)  # [5, 7, 9]
print(a - b)  # [-3, -3, -3]
print(a * b)  # [4, 10, 18]
print(a / b)  # [0.25, 0.4, 0.5]
print(a ** 2)  # [1, 4, 9] (Element-wise square)
print(np.sqrt(a))  # [1. 1.41 1.73]
```

---

## 🔹 7. Aggregation Functions

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])

print(np.sum(arr))  # 21
print(np.mean(arr))  # 3.5
print(np.min(arr))  # 1
print(np.max(arr))  # 6
print(np.std(arr))  # Standard deviation
print(np.var(arr))  # Variance
print(np.cumsum(arr))  # Cumulative sum
print(np.prod(arr))  # Product of elements
```

---

## 🔹 8. Logical Operations

```python
arr = np.array([1, 2, 3, 4, 5])

print(arr > 2)  # [False False  True  True  True]
print(np.any(arr > 4))  # True
print(np.all(arr > 0))  # True
print(np.where(arr > 2, 1, 0))  # [0 0 1 1 1] (1 if > 2 else 0)
print(arr[arr > 2])  # [3 4 5]
```

---

## 🔹 9. Broadcasting

```python
a = np.array([[1], [2], [3]])
b = np.array([4, 5, 6])

print(a + b)
# [[5 6 7]
#  [6 7 8]
#  [7 8 9]]
```

---

## 🔹 10. Stacking Arrays

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(np.vstack((a, b)))  # Stack vertically
print(np.hstack((a, b)))  # Stack horizontally
```

---

## 🔹 11. Splitting Arrays

```python
arr = np.array([1, 2, 3, 4, 5, 6])
print(np.split(arr, 3))  # [array([1,2]), array([3,4]), array([5,6])]
```

---

## 🔹 12. Searching & Filtering

```python
arr = np.array([1, 2, 3, 4, 5])

print(np.where(arr > 3))  # Indices of elements > 3
print(arr[arr > 3])  # [4, 5]
```

---

## 🔹 13. Linear Algebra

```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[2, 0], [1, 3]])

print(np.dot(A, B))  # Matrix multiplication
print(np.linalg.inv(A))  # Inverse of A
print(np.linalg.det(A))  # Determinant of A
print(np.linalg.eig(A))  # Eigenvalues & eigenvectors
```

---

## 🔹 14. Saving & Loading Data

```python
np.save("array.npy", arr)  # Save
loaded_arr = np.load("array.npy")  # Load
```

---

## 🔹 15. Random Sampling

```python
print(np.random.rand(3))  # 3 random values [0,1)
print(np.random.randint(1, 10, 3))  # 3 random integers [1,10)
print(np.random.normal(0, 1, 5))  # 5 samples from normal distribution
```

---

## 🔹 16. Advanced Indexing

```python
arr = np.array([10, 20, 30, 40, 50])
idx = [0, 2, 4]
print(arr[idx])  # [10, 30, 50]
```

---

## 🔹 17. Math Operations

```python
p.add(arr, 2)
np.subtract(arr, 2)
np.multiply(arr, 2)
np.divide(arr, 2)
np.power(arr, 2)
np.exp(arr)
np.sqrt(arr)
np.log(arr)
np.abs(arr)
np.round(arr, 2)
np.sin(arr)
np.cos(arr)
np.tan(arr)
np.arcsin(arr)
np.arccos(arr)
np.arctan(arr)
np.sinh(arr)
...
```

---

## 🔹 18. Statistical Functions

```python
np.mean(arr)
np.median(arr)
np.std(arr)
np.var(arr)
np.min(arr)
np.max(arr)
np.argmax(arr)  # Index of max value
np.argmin(arr)  # Index of min value
```

---

## 🔹 19. Linear Algebra

```python
np.dot(arr1, arr2)  # Dot product
np.linalg.inv(arr)  # Inverse
np.linalg.det(arr)  # Determinant
np.linalg.eig(arr)  # Eigenvalues & Eigenvectors
np.linalg.norm(arr)  # Norm
np.linalg.solve(A, B)  # Solve Ax = B
```

---

## 🔹 20. Unique and Sorting

```python
np.unique(arr)  # Unique elements
np.sort(arr)  # Sort array
np.argsort(arr)  # Indices of sorted elements
```

---

## 🔹 21. Vectorization

```python
def add(a, b):
    return a + b

add = np.vectorize(add)
add([1, 2, 3], [4, 5, 6])


# Vectorize a function
np.vectorize(func)(arr)  # Vectorization
arr.astype(np.float32)  # Reduce memory usage
```
