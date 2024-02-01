```python
#get pytorch 
import torch as tr
#get vector
tr.tensor(1)
#get 1D array
tr.tensor([1,2,3])
#get 2D array
tr.tensor([[1,2],[3,4]])
#get 3D array with desired Data-type
tr.tensor([[[1,2],[4,3]],[[5,6],[8,7]]], dtype=torch.float)
#get dimension of a tensor 
variable.ndim
#get tensor from numpy
tr.from_numpy(variable_of_numpy)
#get a tensor of ones
tr.ones([matrix_row,row,colume])
#get a tensor of ones with different variable shape
tr.ones_like(variable_name)
#get a tensor of zeroes
tr.zeroes



```
**[Dtypes documentation](https://pytorch.org/docs/stable/tensors.html)**
