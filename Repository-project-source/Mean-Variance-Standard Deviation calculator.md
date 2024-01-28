```python
#This line imports numpy module 
import numpy as np
#This function calculates mean, variance, standard deviation, max, min, and the sum of the rows, columns, and elements in a 3 x 3
def calculation(mat):
  #mean
  mean = list(mat.mean(axis=0)), list(mat.mean(axis=1)), mat.mean()
  #variance
  var = list(mat.var(axis=0)), list(mat.var(axis=1)), mat.var()
  #standard deviation
  std = list(mat.std(axis=0)), list(mat.std(axis=1)), mat.std()
  #maximum value
  maxi = list(mat.max(axis=0)), list(mat.max(axis=1)), mat.max()
  #minimun value
  mini = list(mat.min(axis=0)), list(mat.min(axis=1)), mat.min()
  #sum of the rows, columns, and elements
  sums = list(mat.sum(axis=0)), list(mat.sum(axis=1)), mat.sum()
  mean = list(mean)
  var = list(var)
  std = list(std)
  maxi = list(maxi)
  mini = list(mini)
  sums = list(sums)
  print(f'mean :{mean}\nvariance :{var}\nstandard deviation :{std}\nmax :{maxi}\nmin :{mini}\nsum :{sums}')
#This function convert the list into a 3 x 3 matrix and call the calculation function
def calculate(mat):
  try:
    #convert the list into a 3 x 3 matrix
      mat = np.array(mat).reshape(3,3)
      output = calculation(mat)
      return output
  #it will execute if an error occurs  
  except ValueError:
      print('List must contain 9 numbers')
#Test the function with some function
calculate([1,2,3,4,5,6,7,8,9])
calculate([0,1,2,3,4,5,6,7,8])
#will raise an error
calculate([2,6,2,8,4,0,1,5])
```