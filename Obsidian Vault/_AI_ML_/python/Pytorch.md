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
#get datatype of a tensor
varable.dtype
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
#get transpose of a matrix
matrix_variable.T
#get multiplication of tensor
variable.mul(varialbe)
variable*variable
#get matrixmultiplication of tensor
variable.matmul(variable.T)
variable@variable
#get index of element which has max element
tr.argmax(variable)
#get all single dimension removed from targeted sensor
variable.squeeze(dim=0)
#get undo the prvious process
variable.unsqueeze(dim=[1,0])
#get the tensor element to ge permute
tr.permute(variable, (2,0,1), dim=())
#get number of range
tr.range(start,stop,step)
#get reduce-randomness
tr.manual_seed(variable_with_random)
#get the access to GPU 
tr.device('cuda')
#get concate the tensors using stack
tr.stack([vaiable_list],dim=[0->for row, 1->for column])
#get your GPU version
~nvidia.smi
#get your device-set 
"cuda" if torch.cuda.is_available() else "cpu"

```
**[Dtypes documentation](https://pytorch.org/docs/stable/tensors.html)**
Indexing in Pytorch is similar to numpy 
[Pytorch Basic GIT documentation](https://github.com/mrdbourke/pytorch-deep-learning/blob/main/00_pytorch_fundamentals.ipynb)
