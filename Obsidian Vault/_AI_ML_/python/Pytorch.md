```python
#get pytorch 
import torch as tr
#get nn module(it is the building block of neural network)
import torch.nn as nn
#get vector
tr.tensor(1)
#get 1D array
tr.tensor([1,2,3])
#get 2D array
tr.tensor([[1,2],[3,4]])
#get 3D array with desired Data-type
tr.tensor([[[1,2],[4,3]],[[5,6],[8,7]]], dtype=torch.float)
#get datatype of a tensor
varable.dtype #->1
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
!nvidia.smi
#get your device-set 
"cuda" if torch.cuda.is_available() else "cpu"
----the above things are basic of pytorch----
----The below thing will be Advance topic of Machine Learning----
```
<img src="https://raw.githubusercontent.com/mrdbourke/pytorch-deep-learning/main/images/01_a_pytorch_workflow.png" width=900 alt="a pytorch workflow flowchat"/>
*In the below example we are building a model for Linear Regression*
*1.Get the data ready*
```python
#as we don't have data let create one
#weight and bias are the parameter used in linear regression
weight = 0.7
bias = 0.3
x = tr.arange(0,1,0.002, dtype=tr.float32)
y = weight*x + bias
```
*1.1. Get data separated to training and testing*
```python
trainsplit = 0.8*len(x) #allocate 80% of data to training
x_train, y_train = x[:trainsplit], y[:trainsplit]
x_test, y_test = x[trainsplit:], y[trainsplit:]
#create a graph of test data and train data using matplotlib
```
*2. Build a Model*
```python
#to build a model we need to create a class with instance of subclass of nn.Module
#for example let build a model of linear regression
class Linearregression(nn.Module):
#get __init__ function
    def __init__(self):#__init__ always take self as argument(like int main() in C)
        super().__init__()#to get access to function of nn.Module
        self.weights = nn.Parameter(tr.randn(1, dtype=tr.float32), requires_grad = True)
        self.bias = nn.Parameter(tr.randn(1, dtype=tr.float32), requires_grad = True)

    def forward(self, x: tr.tensor) -> tr.tensor:
        return self.weights*x+self.bias
#get defined class by creating an instance of class like below
model_0 = Linearregression()
#get the parameters-list 
model_0.state_dict()
```
*graph code to check the prediction*
```python
def barplot(traindata=x_train, trainlabel=y_train, testdata=x_test, testlabel=y_test, prediction=None):
    plt.figure(figsize=(10,5))
    plt.scatter(traindata,trainlabel,c='g',s=3, label='train')
    plt.scatter(testdata,testlabel,c='b',s=4, label='test')
    if prediction != None:
        plt.scatter(testdata, prediction,c='red', s=5,label='predicteed')
        for i in range(len(prediction)):
            plt.plot([testdata[i], testdata[i]], [prediction[i], testlabel[i]],                                                                                  c='black')
    
    plt.legend()
    plt.grid()
    return plt.show()
```
*2.1 Get loss function and optimizer*
```python
#get loss function for this i have chossen L1Loss you can chosse in ->5
loss_fn = nn.L1Loss() #it bassicaly reduce the loss between the test&predicted value in each ephoes

#get optimizer
optim = tr.optim.SGC(param=model_0, lr: ,momentum:)#refer ->6 for more information
```
*2.2 Get training loop*: ![](https://i.imgur.com/0YWVlYC.png)
```python
# Set the number of epochs (how many times the model will pass over the training data)
epochs=int(input('enter the number of time a model should train'))
for epoch in range(epochs):
### Training
# Put model in training mode (this is the default state of a model)
    model_0.train()
# 1. Forward pass on train data using the forward() method inside 
    y_pred = model_0(X_train)
# 2. Calculate the loss (how different are our models predictions to the ground truth)
    loss = loss_fn(y_pred, y_train)
# 3. Zero grad of the optimizer
    optimizer.zero_grad()
# 4. Loss backwards
    loss.backward()
# 5. Progress the optimizer
    optimizer.step()
```
*3.Train and Evaluate the model*
```python
#inside the previous for loop
model_0.eval()

    with torch.inference_mode():
      # 1. Forward pass on test data
      test_pred = model_0(X_test)

      # 2. Caculate loss on test data
      test_loss = loss_fn(test_pred, y_test.type(torch.float)) # predictions come in torch.float datatype, so comparisons need to be done with tensors of the same type

      # Print out what's happening
      if epoch % 100 == 0:
            epoch_count.append(epoch)
            train_loss_values.append(loss.detach().numpy())
            test_loss_values.append(test_loss.detach().numpy())
            print(f"Epoch: {epoch} | MAE Train Loss: {loss} | MAE Test Loss:                                                                                   {test_loss} ")
```
*4.Check you model with your testing data*
```python
with tr.inference_mode():
	test_pred = model_0(x_test)
#to check your parameter with model
model_0.state_dict()
```
*5.Save the trained model using path*
```python
from pathlib import Path
#create models directory
model = Path('models')
model.mkdir(parent=True,exist_0k=True)
#create a path directory
model_name = 'pytorch-01'
model_name_path = model/modle_name
#save the model
tr.save(obj=model_0.state_dict(),f=model_name_path)
```

1.**[Dtypes documentation](https://pytorch.org/docs/stable/tensors.html)**
2.Indexing in Pytorch is similar to numpy 
3.[Pytorch Basic GIT documentation](https://github.com/mrdbourke/pytorch-deep-learning/blob/main/00_pytorch_fundamentals.ipynb)
4.[Parameter in nn](https://pytorch.org/docs/stable/generated/torch.nn.parameter.Parameter.html#parameter)
5.[Loss functions](https://pytorch.org/docs/stable/nn.html#loss-functions)
6.[Optimizer](https://pytorch.org/docs/stable/optim.html)
7.