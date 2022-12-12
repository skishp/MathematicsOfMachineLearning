In this exercise we will at some given point in the code implement the training and test error. 
To run this jupyter notebook install the following libraries 
```
pip install numpy
pip install scikit-image
pip install matplotlib
```

To solve this exercise we first need to take a look at the definition of a training error. With a `loss function` we can define the training error as the following:
```

If S is a subset of X x Y, where S denotes the training set of size m, then the training error of the classifier h is defined as 
L_S(h)= 1/m Sum_((x,y) in S) l(y,h(x))
```
where `l`denotes the loss function. But know we have to question ourselves what is the loss function and how should it look like. First we note that the loss function should be 0 if the classifier predicts correctly, since we don't want to punish the algorithm for working correctly, besides that loss function can be defined as you wish. For example a commonly used loss function is the 0-1 loss function which is defined as the following 
``` 
l_(0-1)(y_1,y_2) = 0 if y_1 = y_2 and
l_(0-1)(y_1,y_2) = 1 if y_1 != y_2
```
another very popular loss function the `mean-squared-error` (MSE) which is defined as 
```
l_MSE (y_1,y_2) = 1/m Sum (y_1 -y_2)^2
```
Notice that we now indeed use the cardinality of the training set. Contrary to the 0-1 loss function, we punish the algorithm more harshly if the classification is further apart to its true classification. 

The `test error` can be defined analog to the `training error` by using a test set `T` instead of a training set `S`. 

For our exercise we will be using the `MSE` to calculate the training and test error. 