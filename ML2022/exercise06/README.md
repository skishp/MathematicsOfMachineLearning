To run this jupyter notebook you have to install/download some libraries. As already stated in the `README.md` in the parent folder I will be using conda environments. For this exercise you will need to install the following libraries: 
* numpy
* seaborn
* sklearn
* matplotlib
To install them run the following.
```
pip install numpy
pip install seaborn
pip install sklearn
pip install matplotlib
```
Note: I'm not using the conda package installer, since there might be packages which can't be downloaded via conda, and/or the names of the packages are different. 

I will not write down the exercises in this `README.md` since the exercises and solutions are well documented in the jupyter notebook. 

However I will give some of my insights about parts of the code I'm mostly interested in. 

First of all we need some data to work with and also we need the Data to be split in to a Training and Test set. For the data we simply use the provided data set `iris` from `sklearn.datasets`. The splitting is done via
```
x_train, x_test, y_train, y_test = train_test_split(X,y)
```
which is a provided function from the `sklearn.model_selection` library. It randomly splits the data set `X` and the target set `y` into training and test set. 

As we are using a decision tree for this exercise we define our model via
```
model = tree.DecisionTreeClassifier()
```
which is part of the standard `sklearn` library. The first really interesting code snipped is the following
```
model.fit(x_train,y_train)
```
where fitting basically means that we want to train our decision tree given our training set and the corresponding labels. Now that we trained our model, we can let the magic happen, which means we can use it to predict the labels of data. To do that, we use 
```
y_pred = model.predict(x_train)
```
where we used our model to predict the labels of our training set. To calculate the accuracy simply use the 
```
accuracy_score(y_test, y_pred)
```
function. Note: The output of the accuracy with input `y_test,y_pred` is 1 since the training error is 0. This is because 
* we didn't set a bound of the depth of the tree
* it was trained until it perfectly matched the data.
Now we use our model to predict on the test set. When we measure the accuracy again we see that the score is `<1`. 