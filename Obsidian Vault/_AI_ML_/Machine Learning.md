`Introduction`
**[Machine learning](https://www.ibm.com/design/ai/basics/ml/)** is a way of developing a model which can learn on it's own without externally coding. The essence of machine learning and deep learning is to take some data from the past and build an algorithm to predict the future

`example`
Assume you have a cousin who made fortune in real estate  by predicting values in the past, and he says it's just intuition. But more questioning revels that he's identified prize patterns from houses he has seen in the past, and use those pattern to make prediction, ML also works the same way.

`Train-model`
So to train a model we require a knowledge of **Python** library called **scikitlearn** library. so to train a model we use a function known as **[DescisionTreeRegresor](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeRegressor.html)*** before fiting the data make sure to process the data with pandas.

`MODEL-Validation`
After Training a model we should know how much of accuracy it holds, to measure that accuracy we use a function from **scikitlearn** known as [mean_absolute_error](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.mean_absolute_error.html)
`Framework`
In Machine Learning we use several framework like Pytorch, tensorflow, keras, scikit-Learn, MXNet. To train a model.
<img src="https://raw.githubusercontent.com/mrdbourke/pytorch-deep-learning/main/images/01_a_pytorch_workflow.png" width=900 alt="a pytorch workflow flowchat"/>
As we can observe how the workflow is done using the pytorch framework

`Step-to-build-a-model`
 **1. Getting data ready**  :Data can be almost anything but to get started we're going to create a                                             simple straight line 
  **2. Building a model**  :Here we'll create a model to learn patterns in the data, we'll also choose a                                       _loss function, optimizer and build a training loop_.  
**3. Fitting the model to data (training)** : We've got data and a model, now let's let the model                                                                       (try to) find patterns in the (**training**) data. 
 **4. Making predictions and evaluating a model (inference)** :Our model's found patterns in the                                                                       data, let's compare its findings to the actual (**testing**) data. 
 **5. Saving and loading a model** : You may want to use your model elsewhere, or come back to it                                                         later, here we'll cover that. 
 **6. Putting it all together** : Let's take all of the above and combine it. 
