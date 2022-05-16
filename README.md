# House price predictor
_______________________
## Introduction
These notebooks are part of the regression course in ML specialization offered by the University of Washington - Coursera
_______________________
## Simple linear regression (REG01-NB01)
### This is an overview of what the notebook is about.

Regression models describe the relationship between variables by fitting a line to the observed data. in the case of simple linear regression, we only have one input and one output. in this course, we used a case study approach which is predicting house prices.   
our model is just a straight line that is defined by a slope and an intercept.   
![Simple linear regression model](images/simple_model.PNG)  
Now, our task is to try to fit the best possible line for data.   
but how can we define the "best" line?     
First, we need to define a quality metric on which we can measure lines against each other and then choose the best line. this quality metric is the residual sum of squares (RSS). Now our goal is to try to minimize this value for the given coefficients (in our case intercept and slope). the below figure shows what is RSS (depicted as red lines between the data points and the fitted line) and how it's calculated.  

![Simple linear regression model](images/RSS.PNG)  
Now, after we determined the quality metric to choose the best line the next step is "HOW" we are going to find this best line?   
the answer is an algorithm called hill descent in which we compute the gradient of the RSS(the result shown in the figure below), after that, we have two approaches to find the best line:  
1. Analytically (Closed-form Solution).
2. Gradient descent.    

![Simple linear regression model](images/gradients.PNG)  
in this notebook, we will implement method the first method.    
after setting the gradient equal to zero and solving for the slope and intercept we get the following equations:  
![Simple linear regression model](images/w1.PNG) ![Simple linear regression model](images/w0.PNG) 

So, all that is left to do is compute these equations to get the best coefficients that defines the best line which minimizes the cost function. 

________________________________
## Multiple-linear regression (REG02-NB02)
### This is an overview of what the notebook is about.

_____________________________
we discussed in the previous notebook above the simple linear regression, in this notebook we will discuss the multiple-linear regression. in multiple linear regression, we incorporate multiple inputs and a single output. our model will be a polynomial function.   
![multiple-regression model](images/Multi_model.PNG)  
Now, we will use the same cost function we used in the case of simple regression (RSS). but first, we need to write it in matrix notation   
![RSS in matrix nnotation](images/RSS_matrix.PNG)       
where **H** is the feature matrix and **W** is the coefficients vector. Just like simple regression we have two approaches:  
1. Analytically (Closed-form Solution).
2. Gradient descent.   


the closed-form solution is not practical and computationally intensive so we will implement the gradient descent. the algorithm is composed of the following steps:  
1. initialize the coefficients to zero or randomly.
2. loop over the features:  
  2.1 compute the patrial derivative.  
  2.2 update the coefficients.


![RSS in matrix nnotation](images/gradient_algorithm.PNG)
