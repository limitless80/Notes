```python
The Basics
# Get 1D-array with data type
a = np.array([1,2,3], dtype='int32')
# Get 2D-array
b = np.array([[9.0,8.0,7.0],[6.0,5.0,4.0]])
# Get Dimension
a.ndim
# Get Shape
b.shape
# Get Type
a.dtype
# Get Size
a.itemsize
# Get total size
a.nbytes
# Get number of elements
a.size
# Accessing/Changing specific elements, rows, columns, etc
a = np.array([[1,2,3,4,5,6,7],[8,9,10,11,12,13,14]])
# Get a specific element [r, c]
a[1, 5].              b.             b.                      
       b 
# Get a specific row 
a[0, :]        
# Get a specific column
a[:, 2]
#   v. v. v. c. v y b b.      Getting a little more fancy [startindex:endindex:stepsize]
a[0, 1:-1:2]
array([2, 4, 6])
#3-d example
b = np.array([[[1,2],[3,4]],[[5,6],[7,8]]])
# Get specific element (work outside in)
b[0,1,1]
# replace 
b[:,1,:] = [[9,9,9],[8,8]]
# All 0s matrix
np.zeros((2,3))
# All 1s matrix
np.ones((4,2,2), dtype='int32')
# Any other number
np.full((2,2), 99)
# Any other number (full_like)
np.full_like(a, 4)
# Random decimal numbers
np.random.rand(4,2)
# Random Integer values
np.random.randint(-4,8, size=(3,3))
# The identity matrix
np.identity(5)
# Repeat an array
arr = np.array([[1,2,3]])
r1 = np.repeat(arr,3, axis=0)
#Be careful when copying arrays!!!
a = np.array([1,2,3])
b = a.copy()
#Mathematics
a = np.array([1,2,3,4])
a = np.add(a,b)
a = np.sub(a,b)
a = np.multiply(a,b)
a = np.div(a,b)
# Take the sin
np.cos(a)
array([ 0.54030231, -0.41614684, -0.9899925 , -0.65364362])
# For a lot more (https://docs.scipy.org/doc/numpy/reference/routines.math.html)
Linear Algebra
a = np.ones((2,3))
b = np.full((3,2), 2)
np.matmul(a,b)
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
Statistics
stats = np.array([[1,2,3],[4,5,6]])
np.min(stats)
np.max(stats, axis=1)
np.sum(stats, axis=0)
#Reorganizing Arrays
before = np.array([[1,2,3,4],[5,6,7,8]])
after = before.reshape((2,3))
# Vertically stacking vectors
v1 = np.array([1,2,3,4])
v2 = np.array([5,6,7,8])
np.vstack([v1,v2,v1,v2])
# Horizontal  stack
h1 = np.ones((2,4))
h2 = np.zeros((2,2))
np.hstack((h1,h2))
#Miscellaneous
#Load Data from File
filedata = np.genfromtxt('data.txt', delimiter=',')
filedata = filedata.astype('int32')
#Boolean Masking and Advanced Indexing
(~((filedata > 50) & (filedata < 100)))
```