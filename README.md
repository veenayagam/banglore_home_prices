# Prediction of Bangalore House Pricing
# Project Overview 
* Created a tool that predict house pricing in Bangalore to help buyer to know estimate house price which could be useful for budgeting and negotiation.
* Used Bengaluru House price data datasets from Kaggle.(kaggle link provided below)
* Optimized Linear, Lasso, and Random Forest Regressors using GridsearchCV to reach the best model. 
* Built a client facing webpage using flask and heroku 
* Bangalore Home Price Webpage: https://bangalorehomeprices.herokuapp.com/

## Code and Resources Used 
**Python Version:** 3.9  
**Packages:** pandas, numpy, sklearn, matplotlib, sklearn, pickle, flask, json  
**For Web Framework Requirements:**  ```pip install -r requirements.txt```  
**Kaggle Dataset:** https://www.kaggle.com/amitabhajoy/bengaluru-house-price-data

## Data Collection
In the project, the dataset were collected from Kaggle.

## Exploratory Data Analysis
After the data has been collected, we need to clean it up before using in the models. I cleaned and changed variables as follows:

*	Drop features that are not required
*	Remove NA values
*	Split the integer from size column and insert the integer to bhk (Bedrooms Hall Kitchen)
*	Convert Total sqft range values to average of min and max values
*	I analysed which dimension is categorical variable and apply dimensionality reduction technique to reduce number of locations
* Use One Hot Encoding to transform categorical variables into dummy variables
*	Outlier Removal Using Business Logic

Before and after outlier removal: Rajaji Nagar
![rajaji_nagar_outliers](https://user-images.githubusercontent.com/72549846/130307010-a977797b-ced5-496a-8876-a3ad5eb45598.png)

Before and after outlier removal: Hebbal
![hebbal_outliers](https://user-images.githubusercontent.com/72549846/130307025-36e3842e-323a-444e-9037-6dd9d302b52e.png)


## Model Building 
I split the data into train size of 80% and test size of 20% respectively.  

I implemented three different models and evaluated them with different parameters.
I tried three different models:
*	**Multiple Linear Regression** – Baseline for the model
*	**Lasso Regression** – Because of the sparse data from the many categorical variables, a normalized regression like lasso would be effective.
*	**Decision Tree Regressor** – Again with the sparsity associated with the data, I thought that this would be a good fit. 

## Model Performance
The Linear Regression far outperformed the other approaches on the test and validation sets.
Model performance by using GridSearchCV:
*	**Linear Regression** : 84%
*	**Lasso Regression**: 72%
*	**Decision Tree Regressor**: 71%

## Model Deployment
For this step, I built a flask app that was hosted on a Heroku cloud platform. The app takes in a list of values from a form and returns an estimated price. 

