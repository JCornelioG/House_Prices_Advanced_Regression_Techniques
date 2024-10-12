# House_Prices_Advanced_Regression_Techniques

This repo contains simple starter code for the Kaggle beginner level completition 'House Prices: Advanced Regression Techniques'. I wrote these two pieces of code to refresh my knowledge on xgboost and my coding skills with R and Python. Each one takes about one day. Hope you will find it helpful in some way :)

About the dataset
The dataset is a public dataset compiled by Dean De Cock for use in data science education. It's an incredible alternative for data scientists looking for a modernized and expanded version of the often cited Boston Housing dataset.

What Is Included In My Code
Exploratory Data Analysis
Looking at some interesting numeric and categorical variables to understand the data.
Data Cleaning and Preparation
This includes fixing the data types, handling NAs, transforming categorical variables to numeric variables (with one-hot encoding and target encoding), and create simple and intuitive new features (not much feature engineering involved)
Modeling with Xgboost
Here I used the regressor in Xgboost for modeling, and the objective is set to optimize the RMSE of log(SalePrice), which is the same as the evaluation criteria of the competition. Also, I only did a 80/20 split of the training set for model validation, but ideally, you know, you should do a k-fold (especially when there are more data available).
Packages Used
R -- tidyverse (mainly dplyr and ggplot2), xgboost
Python -- numpy, pandas, matplotlib, seaborn, xgboost, scikit-learn (for splitting data only...)

What Can Be Improved From This Code
More EDA + Feature Engineering
I have to admit that I skipped several variables since there are too many... But I think a better way to do it is -- looking at all the variables and do a pre-screening to have some idea which variables could carry more info for your prediction obejective. Then validate it with your feature importance and choose which to drop to avoid noise / make modeling faster. Also, you need to create more features based on the knowledge you gained from EDA and feature importance, and keep testing them and iterate.
K-fold cross-validation
As I mentioned above, I only did a 80/20 split of the training set for model validation here, which is not idea (but for simplicity). One thing to notice is, you need to do target-encoding only with your traning set for each fold, instead of create before CV, which will introduce info leakage.
Tunning Parameters
I did not do a through parameter tunning here, but just played with several values of max_depth, eta and nrounds. But given good feature engineering, tunning hyperparameter is always a good next step to improve your model performance. Some strategies include grid search (comprehesive but computational expensive), random search (faster but not global optimal), bayesian optimization (selects the next hyperparameter value based on the function outputs in the previous iterations).
Model Ensemble
Here only xgboost is used, but more models could be used, from the linear regression to other tree-based models (RF, lightGBM, catboost), or even deep leanring models. Then ensembling the predictions from these models will give a better overall prediction (at least in the case of Kaggle competitions... you know, in real world, we need to think about cost.)
