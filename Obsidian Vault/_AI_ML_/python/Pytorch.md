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
#get tensor of random variable
tr.rand(shape)
#get a tensor of ones with different variable shape and so on
tr.ones_like(variable_name)
tr.rand_like(variable_name)
#get a tensor of zeroes
tr.zeroes([matrix_row,row,colume])
#get tensor from numpy
tr.from_numpy(variable_of_numpy)
#get shape of a tensor
variable.shape
#get datatype of tensor
variable.dtype
#get device that tensor is running
variable.device
#get to know the presence of GPU
if tr.cuda.is_available():
	tensor = tensor.to('cuda')
	print(f"Device tensor is stored on :{tensor}")
#get index access
variable[row,colum]
#get concatination of more tensor variable dim(0->for rowbind, 1->columnbind)
tr.cat([var1,var2,....], dim=1)
#get multiplication of tensor
variable.mul(varialbe)
variable*variable
#get matrixmultiplication of tensor
variable.matmul(variable.T)
variable@variable

```
**[Dtypes documentation](https://pytorch.org/docs/stable/tensors.html)**
