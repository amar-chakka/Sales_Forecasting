# Sales_Forecasting
This is a project in Retail Analytics working on Sales forecasting.

![enter image description here](https://github.com/amar-chakka/Sales_Forecasting/blob/c5e39254e51bd6689bb856a51d50f7b5e254d556/Sales-forecast.png?raw=true)


This project was created as a part of the Retail Analytics  Term project to help an organization in predicting the sales. 
- No business can improve its financial performance without **estimating customer demand** and **future sales** of products/services accurately.

 **WOMart** is a leading nutrition and supplement retail chain that offers a comprehensive range of products for all your wellness and fitness needs.

WOMart follows a multi-channel distribution strategy with 350+ retail stores spread across 100+ cities.

Effective forecasting for store sales gives essential insight into upcoming cash flow, meaning WOMart can more accurately plan the cashflow at the store level.

Sales data for 18 months from 365 stores of WOMart is available along with information on Store Type, Location Type for each store, Region Code for every store, Discount provided by the store on every day, Number of Orders everyday etc.

In this project the outcome is a prediction of sales per store. 

This is a  Data set with 1.88 Million rows  which contains 9 independent variables [int64(3), object(6)] & 1 Target variable [float64].

Most of the features have  anonymous data except Date, Sales Amount and #orders.

There are no Null values in the data frame. There seems to be an outlier in the number of orders there by Sales also.
'Location_Type', 'Store_Type', 'Region_Code', 'Discount' values are one hot encoded.

Using scikit-learn's train_test_split function to split the dataset into train and test sets. 80% of the data will be in the train set and 20% in the test set, as specified by test_size=0.2

**Observations:**
- After perfoming **5-fold** cross-validation on our Baseline Linear Regression model, we get a mean **RMSE** score of **5039.68**

- This means that, our predicted daily sales might have an **error** of more than **5000** in them.

- This is not a good score at all, and we can't use this model in production.
- The **standard deviation** of **28** means that our model is performing almost similarly on each fold it was tested on, and is **generalizing** well on unseen data.

Class is a Target variable. Its imbalanced with No Fraud [0 type] having 248315 [99.83%] & Fraud [1 type] having 492 [0.17%] records of the dataset.

Tried with different regressors with all one hot encoded columns & selective features  over sampled data.

◦RandomForestRegressor
◦DecisionTreeRegressor
◦LinearRegression

RandomForest Regressor is able to predict with MSE: 4530.02 & Standard Deviation: 39.38
Checked  the feature importance of various features. Sorted  the importance by descending order (lowest importance at the bottom)
Performed a K-fold Cross-validation for 5 folds. Able to achieve randomforest model with MSE: 4748.51 Standard Deviation: 22.89
Did a Grid search with RandomForestRegressor as estimator, able to get the optimized model with Mean 

finally, this is the how the predicted Vs Actual values looks for train and Test data. 
![enter image description here](https://github.com/amar-chakka/Sales_Forecasting/blob/39b15f5016a29add761079173ae5c66f9144e423/Model%20Accuracy.png?raw=true)


To check out my notebook, please click [here](https://github.com/amar-chakka/Sales_Forecasting/blob/39b15f5016a29add761079173ae5c66f9144e423/AV_sales_forecasting.ipynb).
