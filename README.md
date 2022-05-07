# Machine-Learning-Project-on-Credit-Card-Applications

## Problem Statement

How can we use the machine learning model to automate the credit card application rather than manual doing?

Let's look into some EDA of the dataset before diving into the project

In this dataset, the count of female is more than count of male, so it is an imbalanced dataset

![Male Female distribution](https://user-images.githubusercontent.com/100771366/167237083-67289f02-3d8d-44e9-b0ca-9d869d530325.jpg)

This graph shows Education vs Income
Even though the data count for males in dataset is almost half compared to female, the graph shows clearly 
that males are earning much high than females.

![Edu vs Income](https://user-images.githubusercontent.com/100771366/167236569-93573a42-e717-4e53-8a15-7ad249da5092.jpg)

This graph shows that commercial associates get the highest salary and 2nd highest is state servants

![Income vs Income type](https://user-images.githubusercontent.com/100771366/167237089-4e747fc7-2efa-4760-96a5-952574d9e8ad.jpg)

This graph showsa that in the occupation type managers earns the most compared to other occupational types

Also the missing values in occupational column have been reclasified as others

![Income vs Occupation type](https://user-images.githubusercontent.com/100771366/167237092-b45472b0-dd29-4210-96f8-6ee855695cf1.jpg)

In this graph we can see that married women and widowed females are earning less compared to others

![Income vs Family Status](https://user-images.githubusercontent.com/100771366/167237097-5028808c-be3e-4c67-b37b-165569d27820.jpg)

In this graph the with parents group males and females are earing less, this could be due to most of them will be students.

![Income vs Housing type](https://user-images.githubusercontent.com/100771366/167237099-85ddbe60-ca36-4323-a30c-d79348627d64.jpg)

These are some of the columns thats we can forcus during the project

The dataset been cleaned, and missing values were treated appropriately without lossing the integrity of the data

The dataset has some outliers, I used winsorisation method to handle the outliers

For example:

Income column before winsorisation 
![Income](https://user-images.githubusercontent.com/100771366/167237587-b6eb1f9f-9250-4e53-8507-6f191d6a887e.jpg)


Income column after winsorisation 
![Win_Income](https://user-images.githubusercontent.com/100771366/167237590-8e34cd5d-d37a-459c-adfb-caddc882cd39.jpg)

Now lets look into the machine learning steps!

This dataset has a lots of categorical data columns and algorithms works will with numerical data rather than categorical.
Thus we will do encoding on the categorical data columns 
I have used dummy encoding, but too many columns can sparse the dataset

Binning is a good way to avoid sparse dataset. I have used binning to narrowdown the occupation column

Next step is Feature Engineering
I have created Age & Employed years column from days birth and days employed columns respectively

Thereafter I have done Vintage Analysis on the 2nd dataset and the final outcome as shown

pic

Label column been labeled according to the table drived, as any past due more than 30 days will be labeled as 1 to represent bad customers

Now we can merge the two datasets

After feature scaling and over sampling to treate the imbalance in the dataset we are ready to deply the model

Before deploying the model we need to choose the appropriate model

I used pycaret and the result as follows:

pic

Feature selection will boost the model perfomance by reducing the complexity
I have used RandomForestClassifier to select top 15 features

Finally I evaluate the model using AUC, because
  ROC AUC is used to measure the performance of an imbalanced dataset model
  Reason: The curve is plotted with True Positive Rate & False Positive Rate 
  Higher AUC higher the model's perfomance
  
Important to do hyperparameter tuning, specially when the model did not perform as expected
I have used RandomForestRegressor

But the untune and tuned model gave the same AUC of 0.71 

This could be due to not enough data in the dataset or overfitting








