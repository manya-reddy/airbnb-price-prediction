# Airbnb-price-prediction
 
Abstract
ML Data Cleaning and Feature Selection Abstract. Airbnb's are the booming options for short time living for travellers. Most people make their side hustle by giving out properties for rent on Airbnb and thus, to be able to predict the value in a city is the purpose of this data analysis.

-The notebook has used various statistics and methods like p-value, t-statistics and visualization techniques like histogram, Q-Q plot, scatter plot and box-plots using various Python libraries like matplotlib, seaborn, etc to answer the below questions about the dataset

-The project aims to perform Exploratory Data Analysis (EDA) on the WHO dataset and implement linear regression model to predict airbnb price in the state of newyork refined through USA.

The following process has been implemented in the project
ABOUT THE DATASET:
- Data processing      
- Imputation
- Performing Imputation by filling the null values of the feature with the corresponding median, mode and mean KNN imputation methods
- Handling outliers
- Feature engineering
- Q-Q PLOT
- Performing Normalisation
- Significance of feature selection
- BUILDING THE MODEL
- Train,Test Split
- Comparing trainig data and testing data
- Linear Regression model
- Predicting with test data
- Evaluating the model using metric
- Important features understanding


Data Set:

Data set consists of:

11 features of an airbnb i.e neighbourhood group, neighbourhood, longitude, latitude, room type, minimum nights, number of reviews, reviews per month, number of reviews itm (in 12 months), state, city.

- Dependent variable is Price
- We have various coordinates in new york city, predicting the best price
- There are 39881 observations with a couple null values
<img width="1076" alt="Screenshot 2023-09-20 at 11 32 20 AM" src="https://github.com/manya-reddy/airbnb-price-prediction/assets/113812925/c0619f4d-187b-4c65-863e-91a778f0d7a8">


Libraries used for this project - 
- Pandas
-  Numpy
- Seaborn
- Matplotlib
- H20
- AutoML

  Softwares Used 
- Jupyter Notebook
- Google Collab


LICENSE- 

MIT License
Copyright (c) 2022 Manimanya Reddy
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


Findings -

Model interpretibility comparision 

1. XGBOOST

The following features have positive impact on the outcome i.e price
1. latitude
2. longitude
The following features have negative impact on the outcome i.e price
1. minimum_nights
2. number_of_reviews
3. availability_365
4. room_type_int

2. Linear regression
The following features have positive impact on the outcome i.e price

1. availibility_356
2. longitude
3. minimun_nights

The following features have negative impact on the outcome i.e price

1. latitude
2. number_of_reviews
3. room_type_int

From the Leaderboard, it can be analysed that the "variable Importance' in Descending order is- 
1. Longitude 
2. Room type
3. Number of reviews
4. availability in 365 days 

For a model to make sense it should follow all the assumptions and have p value, VIF between their respective ranges. RMSE should be as low as possible considering the minimum and maximum values of the target variable, RMSE= 0.0159, model does make sense. To increase the accuracy, some additional variables can be dropped depending on their importance. Furthermore, outliers can be removed or boosting, or ensemble model can be used.

From Shap anaylsis, the feature importance in descending order is -
1. Availability 365 
2. latitude 
3. room type 

While Variables are significant when p-value is less than 0.05. For this model we have longitutude, latitude, room type, availability in 365 days at highest significance.

According to H20 Model-

1. DRF Auto ML model gives      
RMSE- 106.002	
MAE- 46.3874

2. XGBoost Auto ML gives
RMSE - 46.3874.  
MAE - 54.542

3. Stacked Ensemle of all models autoMl gives-
RMSE - 179.716.    
MAE - 79.7295

In a machine learning model, such as a linear regression or random forest model, a partial dependence plot (PDP) is a graphical depiction of the connection between a feature (or set of features) and the target variable.



- Partital dependence on 
1. Number of reviews is very high, which tells us about the contribution of the this feature being very significant. 
2. Longitude and latitude show high peaks and steadiness of plots that signifies a greater impact of contribution through the intervals.
3. Availability 356 shows a steady increase in its impact feature dependence towards dataset
4. minimum no of nights shows a dip in the plot, later being a constant which can be interpreted as lesser significant feature as dataset proceeds
5. room type integer Signifies a steady dependence in the dataset signifying importance of this feature being least.

- XGBoost- A group of decision trees are assembled using XGBoost, and each tree is trained to fix the flaws of the one before it. The model seeks to minimize a cost function that accounts for the discrepancy between expected and actual values. Regularization and early halting are just two of the overfitting prevention strategies the algorithm uses.

By using Kfold and cross validation libraries,

From XGboost analysis we have-

Mean MAE: 2.113 (0.317) 

As the Mean absolute error is analysed to be 2.113, The analysis looks great as error is very less.

From Shap analysis for XgBoost we have- positive values of longitude and number_of_reviews have positive impact on the output

- The Random Forest Regression approach for linear regression is based on the same fundamental ideas as the Random Forest algorithm for classification. It predicts the continuous output variable (i.e the dependent variable) using a set of independent variables rather than predicting the class label of an observation (i.e predictors) via MAE i.e Mean absolute error.  

Random Forest Regression works by creating multiple decision trees on random subsets of the data and features. Each tree is trained on a different subset of the data, and the final prediction is based on the average of the predictions from all the trees.
  


Here, By training and testing the daataset by gitting into the model, we have- 

train MAE = 57.772,       
test MAE = 134.765.

And from The bar plot on importance of features, in descending order we have-
1. Longitutde
2. Availability of airbnb in 365 days
3. latitude 
4. numnber of reviews on airbnb
5. minimum niughts 
6. room type

Shap Analysis- 

A method for explaining the output of machine learning models, particularly linear regression models, is SHAP (SHapley Additive exPlanations) analysis. It sheds light on the relative weights that each feature—an independent variable—has in the model's ability to predict a specific outcome.

We have from the graph as our significant features-
1. Longitude
2. Latitude 
3. Availabilit 365 
4. Room type
and rest being lesser important.

- Heatmap after refining dataset


1. Room_type and availabilty_365 show good negative correlation with target
2. Longitutde, latitude, number of reviews shows a positive correlation with target
3. Minimum nights, room_type has low correlation with our target

QQ plot

<h4>QQ Plots:</h4>

1. Longitude and Latitude QQ plots: The bottom end of the Q-Q plot deviates from the straight line but the upper end is aswell, then we can clearly say that the distribution has a longer tail to its left or simply it is left-skewed and right skewed(or negatively skewed).

2. Availibility_365: The bottom end of the Q-Q plot deviates from the straight line but the upper end is not, then we can clearly say that the distribution has a longer tail and on top to its left or simply it is skewed but better correleated(or negatively skewed).

3. minimum_nights and number_of_reviews: Normally distributed in the start but as the data samples are introduced in increment, the correlation gets irrelevant to the normal distribution





