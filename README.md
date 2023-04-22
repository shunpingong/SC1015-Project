# SC1015 Data Science Project - HDB_resalePrice

## About

This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on resale price of HDB from (https://www.kaggle.com/datasets/teyang/singapore-hdb-flat-resale-prices-19902020). For detailed walkthrough, please view the source code in order from:

1. [Data Preparation](https://github.com/shunpingong/SC1015-Project/blob/main/Data%20Preparation.ipynb) <br>
The code in this notebook is used to extract data from into Numerical and Categorical datasets to gain insights. After data extraction, we explore the different categorical predictors on `resale_price` and dropping some that does not provide valuable information. The remaining categorical predictors are mapped and encoded to aid us for our machine learning later on. The outliers for numerical and categorical are removed and prep to be used in the subsequent notebooks and used as `NumDataCleaned` and `CatDataCleaned` respectively.

2. [Data Visualization For Numerical](https://github.com/shunpingong/SC1015-Project/blob/main/Data%20Visualization%20For%20Numerical.ipynb)<br>
The code in this notebook is used to check the distributions of the numerical predictors on `resale_price`. The correlation of the predictors and the `resale_price` is also obtained to give insights on how the numerical predictors affect `resale_price`.

3. [Data Visualization For Categorical](https://github.com/shunpingong/SC1015-Project/blob/main/Data%20Visualization%20For%20Categorical.ipynb)<br>
The code in this notebook is used to check the distributions of the categrorical predictors on `resale_price`. The correlation of the predictors and the `resale_price` is also obtained to give insights on how the categorical predictors affect `resale_price`.

4. [Linear Regression](https://github.com/shunpingong/SC1015-Project/blob/main/Linear%20Regression.ipynb)<br>
The code in this notebook is used to predict which predictors have the greatest effect on `resale_price`. Univariate regression is being performed on each each of the numerical predictors for both outliers and without outliers and multivariate regression on the numerical predictors. We continued to perform univariate regression on each of the categorical predictors without outliers. `flat_type_num` was found to be the best categorical and `floor_area_sqm` was the best numerical. We further evaluate whether it support what we found by applying it on additional machine learning models in the next 2 notebooks.

5. [Gradient Boosting and Lasso Regression and Random Forest](https://github.com/shunpingong/SC1015-Project/blob/main/Gradient%20Boosting%20and%20Lasso%20Regression%20and%20Random%20Forest.ipynb)<br>
The code in this notebook is used to predict which variable in both `NumDataCleaned` and `CatDataCleaned` are the best in predicting `resale_price`. It is being used into 3 models - Gradient Boosting, Lasso Regression and Random Forest. The features importance of each model is printed to show which few variables are the best and the variables found are being used to compare across all the models to ensure the findings are accurate. In the end, `flat_type_num` and `floor_area_sqm` seems have a very high feature importance in most of these models by consistently having a high feature importance score. Random Forest is also a better model, given it have a higher R^2 value and the lowest MSE. All the models are performed with Cross Validation to get the best hyperparameters to model and used to predict `resale_price` using the predictors

6. [Neural Network](https://github.com/shunpingong/SC1015-Project/blob/main/Neural%20Network.ipynb)<br>
The code in this notebook is used to predict which variable in both `NumDataCleaned` and `CatDataCleaned` are the best in predicting `resale_price`. It uses Neural Network Model and R^2 and MSE of train and test are obtained and compared with previous models and Adam Optimization is used for hypertuning of the parameters to fit the model. We made conclusion on which model is the best by comparing R^2 and MSE across all models and also further confirming our findings of which numerical and categorical predictors are the best. We actually found `floor_area_sqm` and `flat_type_num` to be consistently to be the best numerical and categorical predictors respectively, and neural network also perform worse than random forest, which imply `Random Forest` is the best model to predict `resale_price` of a HDB.
  
## Contributors
- @shunpingong
- @JX531

## Problem Definition

- Given how we are entering into adult life where we have to start getting our own flats
- Housing plays a huge factor on our expenses, we hope to determine
- Which factor affect the resale_price of HDB the most?
- Which model will predict resale_price of HDB the most?
- This is to help us with our expenses when trying to purchase a flat and allow us to make better informed decision to save us costs and cope with rising inflation.

## Models Used

1. Linear Regression
2. Lasso Regression
3. Gradient Boosting
4. Random Forest
5. Neural Network

## Conclusion
1. Briefly summarize your findings in Experiments.<br>
   - `lease_commence_date` seems to have no effect on `resale_price`
   - `floor_area_sqm` seems to be the only numerical predictor affecting `resale_price` from Data Visualisation
   - `flat_type_num` seems to be the best categorical predictor affecting `resale_price` from Data Visualisation 
   - `Linear Regression Model` supports the findings and is used as baseline model
   - `Random Forest Model`perform the best amongst `Gradient Boosting`, `Lasso Regression`, `Neural Network` with the highest R^2 and lowest MSE when predicting `resale_price`
   - Hyperparameters used for `Random Forest Model` are `best_max_depth: 20`   and  ` best_n_estimators: 500` <br>

2. The limitation of your current model. How you can improve your model.
   - Hyperparameters Of Models might not be the best as we only use a few choices
   - Current tuning of hyperparameters is taking a significant amount of time, can reduce rows of data if necessary
   - Too many rows of data so could not perform Cross Validation or Grid Search for extensive amount of combinations to find the best hyperparameters
   - To improve our model, rows of data that are irrelevant or excess can be cut down so we can include more hyperparameters to be tested against to figure the best
   - Only 5 columns are tested against `resale_price`, could have added more columns from additional excel sheets to be tested together to provide more insights

   
## What did we learn from this project?
1. Basic Usages Of New Models
- Neural Netowrk
- Random Forest 
- Gradient Boosting
- Lasso Regression

2. New Techniques For Analysis and Hyperparameter tuning
- Cross Validation
- Adam Optimization
- Feature Importance
- Grid Search

3. Combining Of Techniques With Models
- Random Forest and Grid Search
- Neural Network and Adam Optimization
- Lasso Regression and Cross Validation
- Gradient Boosting and Grid Search
- Implementing Feature Importance Techique with all the models to determine predictors with high importance

## References

- <https://medium.com/fintechexplained/what-is-grid-search-c01fe886ef0a#:~:text=Grid%20search%20is%20a%20tuning,us%20time%2C%20effort%20and%20resources.>
- <https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.GradientBoostingRegressor.html>
- <https://www.analyticsvidhya.com/blog/2021/06/understanding-random-forest/>
- <https://vitalflux.com/lasso-ridge-regression-explained-with-python-example/>
- <https://machinelearningmastery.com/calculate-feature-importance-with-python/>
- <https://machinelearningmastery.com/tutorial-first-neural-network-python-keras/>
- <https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LassoCV.html>
- <https://www.tensorflow.org/api_docs/python/tf/keras/optimizers/Adam>
