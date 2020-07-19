# Project 2 - Ames Housing Data and Kaggle Challenge

## Problem Statement

Identify the features that play an important role in the predicting the home price in Ames, Iowa.

## Kaggle Data Set and Resources

1. Click this link ([Regression Challenge Sign Up](https://www.kaggle.com/t/cf68f4a276f44b59a3c6c843dbf9ed1e)) to **join** the competition
2. Review the material on the [DSI-US-6 Regression Challenge](https://www.kaggle.com/c/dsi-us-6-project-2-regression-challenge)
3. Review the [data description](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt).

## Overview

- The train set has a total of 81 columns including the target variable 'Sale Price' and 2051 rows.
- The test set has a total of 80 columns excluding the target variable 'Sale Price' and 879 rows.
- Notice a missing column from the data set 'Sale Condition' as per special notes provided.
- Both train and data set columns are made up of 23 Nominal, 23 Ordinal, 14 Discrete and 20 Continous variables.

- The top 5 neighborhoods with the highest number of home sales are NAmes, CollgCr, OldTown, Edwards and Somerst.
- Most of the home sales done from 2006 to 2010 with a saleprice of 100,000 to 200,000 USD
- Average price for a home in Ames between 2006 and 2010 is around $ 181,470
- NAmes seems to be the most popular, with 310 home sales almost twice the number of sales to the second place CollgCr at 180 home sales.
- Veenker, Blueste, Greens, Grnhill and Landmrk made up the bottom 5 with least number of home sales

## The Modeling Process

1. The train dataset has all of the columns that you will need to generate and refine your models. The test dataset has all of those columns except for the target that you are trying to predict in your Regression model.
2. Generate your regression model using the training data. We expect that within this process, you'll be making use of:
    - train-test split
    - cross-validation / grid searching for hyperparameters
    - strong exploratory data analysis to question correlation and relationship across predictive variables
    - code that reproducibly and consistently applies feature transformation (such as the preprocessing library)
3. Predict the values for your target column in the test dataset and submit your predictions to Kaggle to see how your model does against unknown data.
    - **Note**: Kaggle expects to see your submissions in a specific format. Check the challenge's page to make sure you are formatting your CSVs correctly!
    - **You are limited to models you've learned in class**. In other words, you cannot use XGBoost, Neural Networks or any other advanced model for this project.
4. Evaluate your models!
    - consider your evaluation metrics
    - consider your baseline score

## Conclusion and Recommendation

- After running the model for Linear Regression, Lasso, Ridge and Elastic Net, I notice Lasso and Elastic Net scored the highest at 89.54 while Linear Regression has a negative R-Square which might be due to overfitting.
- Unlike Linear Regression, both Lasso and Ridge are able to handle multicollinearity hence there's only slight difference in their score with Ridge R square at 88.56. 
- Hence used the Lasso model as it also deals with feature selection of variables helping to eliminate the redundant ones.
- Lasso model did well during the evaluation with an R-Square Score of 0.906

- Based on the blog for home buyers in the US, the 8 most important factors that incluences the home value are Neighborhood Comps( Comparison Price), Location, Home Size and Usable space, Age and Conditon, Upgrades, Timing, Economy and Interest Rates.
- And based on our model we can see the Neighborhood Northbridge Heights and Stonebrook does play an role in with regards to home value as the average home price is more than USD 300,000 while the average home price in Ames is around USD 181,000.
- Our model also shows total_flr_size feature with the highest coefficient.
- The property age feature has the lowest coefficient to sale price, which makes sense as the older home is more issues will arise.
- For property sellers, condition of the home will play a huge factor in determining the sale price. As you will be able to see 5 out of the 8 features is related to the condition of the home(eg: overall quality, exterior quality, overall condition etc)
- As we notice from our eda section with home sales its based on a seasonal cycle, with the peak period in summer months and low periods in the winter months.
- One thing I noticed, the housing market unlike other US states is stable as during the 2008 financial crisis I didnt see a decrease or change in pattern compared to the other years.

Reference <br>
https://www.opendoor.com/w/blog/factors-that-influence-home-value
