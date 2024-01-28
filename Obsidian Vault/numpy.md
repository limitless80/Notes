```python
### Load in NumPy (remember to pip install numpy first)

import numpy as np

### The Basics

a = np.array([1,2,3], dtype='int32')
print(a)

[1 2 3]

b = np.array([[9.0,8.0,7.0],[6.0,5.0,4.0]])
print(b)

[[9. 8. 7.]
 [6. 5. 4.]]

# Get Dimension
a.ndim

1

# Get Shape
b.shape

(2, 3)

# Get Type
a.dtype

dtype('int32')

# Get Size
a.itemsize

4

# Get total size
a.nbytes

12

# Get number of elements
a.size

3

### Accessing/Changing specific elements, rows, columns, etc

a = np.array([[1,2,3,4,5,6,7],[8,9,10,11,12,13,14]])
print(a)

[[ 1  2  3  4  5  6  7]
 [ 8  9 10 11 12 13 14]]

# Get a specific element [r, c]
a[1, 5]

13

# Get a specific row 
a[0, :]

array([1, 2, 3, 4, 5, 6, 7])

# Get a specific column
a[:, 2]

array([ 3, 10])

# Getting a little more fancy [startindex:endindex:stepsize]
a[0, 1:-1:2]

array([2, 4, 6])

a[1,5] = 20

a[:,2] = [1,2]
print(a)

[[ 1  2  5  4  5  6  7]
 [ 8  9  5 11 12 20 14]]
[[ 1  2  1  4  5  6  7]
 [ 8  9  2 11 12 20 14]]

*3-d example

b = np.array([[[1,2],[3,4]],[[5,6],[7,8]]])
print(b)

[[[1 2]
  [3 4]]

 [[5 6]
  [7 8]]]

# Get specific element (work outside in)
b[0,1,1]

4

# replace 
b[:,1,:] = [[9,9,9],[8,8]]

---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-34-db1aebb5daad> in <module>()
      1 # replace
----> 2 b[:,1,:] = [[9,9,9],[8,8]]

ValueError: setting an array element with a sequence.

b

array([[[1, 2],
        [9, 9]],

       [[5, 6],
        [8, 8]]])

### Initializing Different Types of Arrays

# All 0s matrix
np.zeros((2,3))

array([[0., 0., 0.],
       [0., 0., 0.]])

# All 1s matrix
np.ones((4,2,2), dtype='int32')

array([[[1, 1],
        [1, 1]],

       [[1, 1],
        [1, 1]],

       [[1, 1],
        [1, 1]],

       [[1, 1],
        [1, 1]]])

# Any other number
np.full((2,2), 99)

array([[99., 99.],
       [99., 99.]], dtype=float32)

# Any other number (full_like)
np.full_like(a, 4)

array([[4, 4, 4, 4, 4, 4, 4],
       [4, 4, 4, 4, 4, 4, 4]])

# Random decimal numbers
np.random.rand(4,2)

array([[0.07805642, 0.53385716],
       [0.02494273, 0.99955252],
       [0.48588042, 0.91247437],
       [0.27779213, 0.16597751]])

# Random Integer values
np.random.randint(-4,8, size=(3,3))

array([[-2, -4, -4],
       [ 6,  6,  3],
       [ 3,  2,  2]])

# The identity matrix
np.identity(5)

array([[1., 0., 0., 0., 0.],
       [0., 1., 0., 0., 0.],
       [0., 0., 1., 0., 0.],
       [0., 0., 0., 1., 0.],
       [0., 0., 0., 0., 1.]])

# Repeat an array
arr = np.array([[1,2,3]])
r1 = np.repeat(arr,3, axis=0)
print(r1)

[[1 2 3]
 [1 2 3]
 [1 2 3]]

output = np.ones((5,5))
print(output)

z = np.zeros((3,3))
z[1,1] = 9
print(z)

output[1:-1,1:-1] = z
print(output)

[[1. 1. 1. 1. 1.]
 [1. 1. 1. 1. 1.]
 [1. 1. 1. 1. 1.]
 [1. 1. 1. 1. 1.]
 [1. 1. 1. 1. 1.]]
[[0. 0. 0.]
 [0. 9. 0.]
 [0. 0. 0.]]
[[1. 1. 1. 1. 1.]
 [1. 0. 0. 0. 1.]
 [1. 0. 9. 0. 1.]
 [1. 0. 0. 0. 1.]
 [1. 1. 1. 1. 1.]]

##### Be careful when copying arrays!!!

a = np.array([1,2,3])
b = a.copy()
b[0] = 100

print(a)

[1 2 3]

### Mathematics

a = np.array([1,2,3,4])
print(a)

[1 2 3 4]

a + 2

array([5, 6, 7, 8])

a - 2

array([-1,  0,  1,  2])

a * 2

array([2, 4, 6, 8])

a / 2

array([0.5, 1. , 1.5, 2. ])

b = np.array([1,0,1,0])
a + b

array([1, 0, 3, 0])

a ** 2

array([ 1,  4,  9, 16], dtype=int32)

# Take the sin
np.cos(a)

array([ 0.54030231, -0.41614684, -0.9899925 , -0.65364362])

# For a lot more (https://docs.scipy.org/doc/numpy/reference/routines.math.html)

##### Linear Algebra

a = np.ones((2,3))
print(a)

b = np.full((3,2), 2)
print(b)

np.matmul(a,b)

[[1. 1. 1.]
 [1. 1. 1.]]
[[2 2]
 [2 2]
 [2 2]]

array([[6., 6.],
       [6., 6.]])

# Find the determinant
c = np.identity(3)
np.linalg.det(c)

1.0

## Reference docs (https://docs.scipy.org/doc/numpy/reference/routines.linalg.html)

# Determinant
# Trace
# Singular Vector Decomposition
# Eigenvalues
# Matrix Norm
# Inverse
# Etc...

##### Statistics

stats = np.array([[1,2,3],[4,5,6]])
stats

array([[1, 2, 3],
       [4, 5, 6]])

np.min(stats)

1

np.max(stats, axis=1)

array([3, 6])

np.sum(stats, axis=0)

array([5, 7, 9])

### Reorganizing Arrays

before = np.array([[1,2,3,4],[5,6,7,8]])
print(before)

after = before.reshape((2,3))
print(after)

[[1 2 3 4]
 [5 6 7 8]]

---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-151-6aa1f4e15729> in <module>()
      2 print(before)
      3 
----> 4 after = before.reshape((2,3))
      5 print(after)

ValueError: cannot reshape array of size 8 into shape (2,3)

# Vertically stacking vectors
v1 = np.array([1,2,3,4])
v2 = np.array([5,6,7,8])

np.vstack([v1,v2,v1,v2])

array([[1, 2, 3, 4],
       [5, 6, 7, 8],
       [1, 2, 3, 4],
       [5, 6, 7, 8]])

# Horizontal  stack
h1 = np.ones((2,4))
h2 = np.zeros((2,2))

np.hstack((h1,h2))

array([[1., 1., 1., 1., 0., 0.],
       [1., 1., 1., 1., 0., 0.]])

### Miscellaneous

##### Load Data from File

filedata = np.genfromtxt('data.txt', delimiter=',')
filedata = filedata.astype('int32')
print(filedata)

[[  1  13  21  11 196  75   4   3  34   6   7   8   0   1   2   3   4   5]
 [  3  42  12  33 766  75   4  55   6   4   3   4   5   6   7   0  11  12]
 [  1  22  33  11 999  11   2   1  78   0   1   2   9   8   7   1  76  88]]

##### Boolean Masking and Advanced Indexing

(~((filedata > 50) & (filedata < 100)))

array([[ True,  True,  True,  True,  True, False,  True,  True,  True,
         True,  True,  True,  True,  True,  True,  True,  True,  True],
       [ True,  True,  True,  True,  True, False,  True, False,  True,
         True,  True,  True,  True,  True,  True,  True,  True,  True],
       [ True,  True,  True,  True,  True,  True,  True,  True, False,
         True,  True,  True,  True,  True,  True,  True, False, False]])
```