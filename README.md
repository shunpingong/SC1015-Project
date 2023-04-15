# SC1015 Data Science Project - HDB_resalePrice

## About

This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on resale price of HDB from (https://www.kaggle.com/datasets/teyang/singapore-hdb-flat-resale-prices-19902020). For detailed walkthrough, please view the source code in order from:

1. [Data Preparation](https://github.com/shunpingong/SC1015-Project/blob/main/Data%20Preparation.ipynb) <br>
The code in this notebook is used to extract data from into Numerical and Categorical datasets to gain insights. After data extraction, we explore the different categorical predictors on `resale_price` and dropping some that does not provide valuable information. The remaining categorical predictors are mapped and encoded to aid us for our machine learning later on. The outliers for numerical and categorical are removed and prep to be used in the subsequent notebooks and used as `NumDataCleaned` and `CatDataCleaned` respectively.

2. [Data Visualization For Numerical](https://github.com/shunpingong/SC1015-Project/blob/main/Data%20Visualization%20For%20Numerical.ipynb)<br>
The code in this notebook is used to check the distributions of the numerical predictors on `resale_price`. The correlation of the predictors and the `resale_price` is also obtained to give insights on how the numerical predictors affect `resale_price`.

3. [Data Visualization For Categorical](https://github.com/shunpingong/SC1015-Project/blob/main/Data%20Visualization%20For%20Categorical.ipynb)<br>
The code in this notebook is used to check the distributions of the categrorical predictors on `resale_price`. The correlation of the predictors and the `resale_price` is also obtained to give insights on how the categorical predictors affect `resale_price`.

4. [Linear Regression](https://github.com/shunpingong/SC1015-Project/blob/main/Linear%20and%20Multivariate%20Regression.ipynb)<br>
The code in this notebook is used to predict which predictors have the greatest effect on `resale_price`. Univariate regression is being performed on each each of the numerical predictors for both outliers and without outliers and multivariate regression on the numerical predictors. We continued to perform univariate regression on each of the categorical predictors without outliers. `flat_type_num` was found to be the best categorical and `floor_area_sqm` was the best numerical. We further evaluate whether it support what we found by applying it on additional machine learning models in the next 2 notebooks.


5. [Gradient Boosting and Lasso Regression and Random Forest](https://github.com/shunpingong/SC1015-Project/blob/main/Gradient%20Boosting%20and%20Lasso%20Regression%20and%20Random%20Forest.ipynb)<br>
The code in this notebook is used to predict which variable in both `NumDataCleaned` and `CatDataCleaned` are the best in predicting `resale_price`. It is being used into 3 models - Gradient Boosting, Lasso Regression and Random Forest. The features importance of each model is printed to show which few variables are the best and the variables found are being used to compare across all the models to ensure the findings are accurate. In the end, `flat_type_num` and `floor_area_sqm` seems have a very high feature importance in most of these models by consistently having a high feature importance score. Random Forest is also a better model, given it have a higher R^2 value and the lowest MSE.

6. [Neural Network](https://github.com/shunpingong/SC1015-Project/blob/main/Neural%20Network.ipynb)<br>
The code in this notebook is used to predict which variable in both `NumDataCleaned` and `CatDataCleaned` are the best in predicting `resale_price`. It uses Neural Network Model and R^2 and MSE of train and test are obtained and compared with previous models. We made conclusion on which model is the best by comparing R^2 and MSE across all models and also further confirming our findings of which numerical and categorical predictors are the best. We actually found `floor_area_sqm` and `flat_type_num` to be consistently to be the best numerical and categorical predictor, and neural network also perform worse than random forest. 
  
## Contributors
- @shunpingong
- @JX531

## Problem Definition

- Given how we are entering into adult life where we have to start getting our own flats, we hope to determine
- Which factor affect the resale_price of HDB the most?
- Which model will predict resale_Price of HDB the most?
- This is to help us with our expenses when trying to purchase a flat

## Models Used

1. Linear Regression
2. Lasso Regression
3. Gradient Boosting
4. Random Forest
5. Neural Network

## Conclusion
1. Briefly summarize your findings in Experiments.
   -
2. The limitation of your current model. How you can improve your model.
   -
   
## What did we learn from this project?


## References

- <>
