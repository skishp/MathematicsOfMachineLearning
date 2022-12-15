To run this jupyter notebook you should install the following packages. 
```
pip install numpy
pip install scikit-image
pip install ipywidgets
```
This exercise isn't really a challenge to code, but this will be more about learning and understanding the `Perceptron` model. The algorithm for the binary classifier will terminate successfully if the Data set can be separated. The definition of this can be visualized in the first Plot. Notice that the points of each class can be indeed separated with a line. However our first assignment is, to add a data point such that the `Perceptron` model will fail. 

To do that we have to exchange to point `[0,2]` to for example `[2,-2]`. We assign this point to the class 1. This point will lie in the middle of the point cloud of the class two, which results in a not terminating algorithm. You still will be able to run this code, since its programmed to stop after 100 iterations without finding a solution. 

In the last cell of this exercise you will find a visualization of this problem. 