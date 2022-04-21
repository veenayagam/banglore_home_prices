# Prediction of Bangalore House Pricing
# Project Overview 
* Created a tool that predicts house pricing in Bangalore to help buyers to know estimate house prices which could be useful for budgeting and negotiation.
* Optimized Linear, Lasso, and Random Forest Regressors using GridsearchCV to reach the best model. 
* Built a client-facing webpage using Flask and Heroku.
* Bangalore Home Price Webpage can be accessed [here](https://bangalorehomeprices.herokuapp.com/).

## Code and Resources Used 
**Python Version:** 3.9  
**Packages:** pandas, numpy, sklearn, matplotlib, sklearn, pickle, flask, json  
**For Web Framework Requirements:**  ```pip install -r requirements.txt```  
**Kaggle Dataset:** https://www.kaggle.com/amitabhajoy/bengaluru-house-price-data

## Data Collection
For the project, the dataset was collected from Kaggle.

## Feature Engineering
After the data has been collected, it undergoes cleaning before using in the models. The data has been cleaned and changed variables were as follows:

*	Drop features that are not required
*	Remove NA values
*	Split the integer from size column and insert the integer to bhk (Bedrooms Hall Kitchen)
*	Convert Total sqft range values to an average of min and max values
*	Analysed which dimension is categorical variable and apply dimensionality reduction technique to reduce the number of locations
* Use One Hot Encoding to transform categorical variables into dummy variables
*	Outlier Removal Using Business Logic

Before and after outlier removal: Rajaji Nagar
![rajaji_nagar_outliers](https://user-images.githubusercontent.com/72549846/130307010-a977797b-ced5-496a-8876-a3ad5eb45598.png)

Before and after outlier removal: Hebbal
![hebbal_outliers](https://user-images.githubusercontent.com/72549846/130307025-36e3842e-323a-444e-9037-6dd9d302b52e.png)


## Model Building 
The data has been split into train size of 80% and test size of 20% respectively.  

Three different models have been implemented and evaluated with different parameters.
Below are the different models:
*	**Linear Regression** – Used as a baseline for the model.
*	**Lasso Regression** – Used because normalized regression like lasso would be effective for sparse data from the many categorical variables.
*	**Decision Tree Regressor** – Used because again with the sparsity associated with the data, this model would be a good fit.

## Model Performance
The Linear Regression far outperformed the other approaches on the test and validation sets.
Model performance by using GridSearchCV:
*	**Linear Regression** : 84%
*	**Lasso Regression**: 72%
*	**Decision Tree Regressor**: 71%

## Model Deployment
For this step, the Flask app has been built and hosted on a Heroku cloud platform. The app takes in a list of values from a form and returns an estimated price.
