# Neural_Network_Charity_Analysis

## Overview of the analysis

This project creates a binary classifier neural network machine learning model that will analyze a dataset containing 34,000 entries of organizations which have been funded by a company called Alphabet Soup to predict whether a new organization will be successful upon receiving charity from Alphabet Soup in the future.

### Purpose

Predicting whether an organization can be benefitted by Alphabet Soup's charity will help Alphabet Soup decide who to give money to and who to avoid giving charity to, which will enable them to spend their resources in a smarter way.

## Results

Before I mention my findings, lets take a look at the dataset itself. Here are all the columns of the dataset:

![Features](https://github.com/Zarif601/Neural_Network_Charity_Analysis/blob/main/Resources/Images/Features.PNG)

#### Data Preprocessing

1. The target variable from this dataset is 'IS_SUCCESSFUL,' which shows us whether the organization made good use of the money received from Alphabet Soup or not.

2. The features were determined to be: 'APPLICATION_TYPE,' 'AFFILIATION,' 'CLASSIFICATION,' 'USE_CASE,' 'ORGANIZATION,' 'STATUS,' 'INCOME_AMT,' 'SPECIAL_CONSIDERATIONS,' and 'ASK_AMT.'

3. The columns 'EIN,' and 'NAME' were thought to not add much value to the analysis and were dropped from the input dataset initially.

#### Compiling, Training, and Evaluating the Model

1. For the initial analysis I opted to use three layers for my neural network model. The first layer consisted of 80 neurons and used the 'relu' activation function, the second layer had 30 neurons and also used the 'relu activation function since it is the fastest and considered to work very well with non-linear data. The third and final layer, which is the output layer, only had one neuron and used the 'sigmoid' activation function to predict a probability value for the output. Here is what the model looks like:

![Unoptimized Model](https://github.com/Zarif601/Neural_Network_Charity_Analysis/blob/main/Resources/Images/Unoptimized%20Model.PNG)

This model generated an accuracy score of around 72% which is not very high. Here are the accuracy result achieved from this model:

![Unoptimized Accuracy](https://github.com/Zarif601/Neural_Network_Charity_Analysis/blob/main/Resources/Images/Unoptimized%20Accuracy.PNG)

2. The goal is to achieve atleast 75% or more accuracy with a model for this dataset. After trying various different things, changing the number of layers, the number of neurons in each layer, playing around with the activation functions and dropping some of the features from the dataset, nothing seemed to work. However, after a lot of tweaking I was able to get to the threshold of 75% accuracy or more. Here is what the model looks like after reintroducing the 'NAME' column:

![Optimized Model](https://github.com/Zarif601/Neural_Network_Charity_Analysis/blob/main/Resources/Images/Optimized%20Model.PNG)

The accuracy generated from this model was around 77% which isn't too big of a difference, but atleast it reaches our threshold. Here is how the accuracy was measured:

![Optimized Accuracy](https://github.com/Zarif601/Neural_Network_Charity_Analysis/blob/main/Resources/Images/Optimized%20Accuracy.PNG)

3. The model performance rose after I kept the 'NAME' columnwith my input data instead of dropping it. What is even more interesting is that when I tried to one-hot-encode the 'NAME' column, since it contains categorical data, the more amount of entries I binned the lower my accuracy score got. This is counterintuitive because the name of the organization who is receiving the donation should not actually impact whether that organization would be successful in their goals or not by receiving charity from Alphabet Soup. However, the model's accuracy rose significantly due to this change.

## Summary

The results of the initial model was not the best since the accuracy of the model was below 75%. Reintroducing the 'NAME' column back into the input data increased model accuracy, but thinking about it logically, it shouldn't have any impact in predicting our target variables. Overall, it seems like for this dataset we need to experiment with different other models to see if they can perform better. Random Forest can be a good fit since it emphasizes feature selection by weighing certain features as more important than others. Further investigation is required.
