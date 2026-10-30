# NumPy Vectorization and Broadcasting

## Aim

Perform arithmetic operations on complete NumPy arrays and understand
broadcasting between arrays of compatible shapes.

## Objective

Understand efficient numerical computation using NumPy without writing
unnecessary Python loops.

## Tools Required

-   Python
-   NumPy
-   Jupyter Notebook

## 1. Import NumPy

``` python
import numpy as np
```

## 2. Vectorized Arithmetic Operations

Vectorization means performing an operation on all elements of an array
at once, without using an explicit `for` loop.

``` python
import numpy as np

# Create two NumPy arrays
a = np.array([10, 20, 30, 40])
b = np.array([1, 2, 3, 4])

print("Addition:", a + b)
print("Subtraction:", a - b)
print("Multiplication:", a * b)
print("Division:", a / b)
print("Square of a:", a ** 2)
```

### Output

``` text
Addition: [11 22 33 44]
Subtraction: [ 9 18 27 36]
Multiplication: [ 10  40  90 160]
Division: [10. 10. 10. 10.]
Square of a: [ 100  400  900 1600]
```

## 3. Broadcasting Examples

Broadcasting allows NumPy to perform operations on arrays with different
but compatible shapes.

### Example 1: Adding a scalar to an array

``` python
import numpy as np

numbers = np.array([10, 20, 30, 40])
result = numbers + 5

print("Original array:", numbers)
print("After adding 5:", result)
```

Output:

``` text
Original array: [10 20 30 40]
After adding 5: [15 25 35 45]
```

### Example 2: Adding a row array to a 2D array

``` python
import numpy as np

matrix = np.array([[1, 2, 3],
                   [4, 5, 6]])

row = np.array([10, 20, 30])

result = matrix + row

print("Result:")
print(result)
```

Output:

``` text
Result:
[[11 22 33]
 [14 25 36]]
```

### Example 3: Adding a column array to a 2D array

``` python
import numpy as np

matrix = np.array([[1, 2, 3],
                   [4, 5, 6]])

column = np.array([[10],
                   [20]])

result = matrix + column

print("Result:")
print(result)
```

Output:

``` text
Result:
[[11 12 13]
 [24 25 26]]
```

## 4. Loop-Based Calculation

In this method, we use a `for` loop to add two arrays element by
element.

``` python
import numpy as np

a = np.array([10, 20, 30, 40])
b = np.array([1, 2, 3, 4])

result = []

for i in range(len(a)):
    result.append(a[i] + b[i])

print("Loop-based result:", result)
```

Output:

``` text
Loop-based result: [11, 22, 33, 44]
```

## 5. Vectorized Calculation

The same operation can be performed directly using NumPy.

``` python
import numpy as np

a = np.array([10, 20, 30, 40])
b = np.array([1, 2, 3, 4])

result = a + b

print("Vectorized result:", result)
```

Output:

``` text
Vectorized result: [11 22 33 44]
```

## 6. Comparison: Loops vs Vectorization

  -----------------------------------------------------------------------
  Loop-Based Calculation              Vectorized Calculation
  ----------------------------------- -----------------------------------
  Uses explicit `for` loops.          Uses NumPy array operations.

  Requires more lines of code.        Requires fewer lines of code.

  Often slower for large numerical    Usually faster for large numerical
  arrays.                             arrays.

  Processes elements one by one in    Performs operations on whole
  Python.                             arrays.
  -----------------------------------------------------------------------

## 7. Conclusion

NumPy vectorization makes numerical calculations simpler and often
faster by applying operations to complete arrays. Broadcasting allows
operations between arrays of compatible shapes without manually
repeating values or writing loops.

## Interview Questions

**1. What is NumPy?**\
NumPy is a Python library used for numerical calculations and working
with arrays.

**2. What is vectorization?**\
Vectorization is performing operations on complete arrays without
writing explicit Python loops.

**3. What is broadcasting?**\
Broadcasting is a NumPy feature that allows operations between arrays of
compatible shapes.

**4. What is the advantage of vectorization?**\
It makes code shorter, easier to read, and often faster.

**5. Can arrays with different shapes be added?**\
Yes, if their shapes are compatible under NumPy broadcasting rules.
