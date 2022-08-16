# NYC-Taxi-Trip-Time-Prediction-ML
Machine Learning project on supervised ml algorithm

In this playground competition, hosted in partnership with Google Cloud and Coursera, you are tasked with predicting the fare amount (inclusive of tolls) for a taxi ride in New York City given the pickup and dropoff locations. While you can get a basic estimate based on just the distance between the two points, this will result in an RMSE of $5-$8, depending on the model used. Your challenge is to do better than this using Machine Learning techniques! 

## File descriptions
* train.csv - Input features and target fare_amount values for the training set (about 55M rows). 
* test.csv - Input features for the test set (about 10K rows). Your goal is to predict fare_amount for each row.
* sample_submission.csv - a sample submission file in the correct format (columns key and fare_amount). This file 'predicts' fare_amount to be $11.35 for all rows, which is the mean fare_amount from the training set.
## Data fields
* key - Unique string identifying each row in both the training and test sets. Comprised of pickup_datetime plus a unique integer, but this doesn't matter, it should just be used as a unique ID field. Required in your submission CSV. Not necessarily needed in the training set, but could be useful to simulate a 'submission file' while doing cross-validation within the training set.
* pickup_datetime - timestamp value indicating when the taxi ride started.
* pickup_longitude - float for longitude coordinate of where the taxi ride started.
* pickup_latitude - float for latitude coordinate of where the taxi ride started.
* dropoff_longitude - float for longitude coordinate of where the taxi ride ended.
* dropoff_latitude - float for latitude coordinate of where the taxi ride ended.
* passenger_count - integer indicating the number of passengers in the taxi ride.
* fare_amount - float dollar amount of the cost of the taxi ride. This value is only in the training set; this is what you are predicting in the test set and it is required in your submission CSV.

## Dataset Download
* https://www.kaggle.com/c/new-york-city-taxi-fare-prediction/data <br>
This dataset contains information on default payments, demographic factors, credit limit, history of payments, and bill statements of credit card clients in Taiwan from April 2005 to September 2005.


Machine Learning Models Used: 
1. Logistic Regression
2. Random Forest
3. XGBoost

## Key Findings from EDA
1. Males have more delayed payment than females in this dataset. Keep in mind that this finding only applies to this dataset, it does not imply this is true for other datasets.
2. Customers with higher education have less default payments and higher credit limits.
3. Customers aged between 30-50 have the lowest delayed payment rate, while younger groups (20-30) and older groups (50-70) all have higher delayed payment rates. However, the delayed rate drops slightly again in customers older than 70.
4. There appears to be no correlation between default payment and marital status.
5. Customers being inactive doesn’t mean they have no default risk. We found 317 out of 870 inactive customers who had no consumption in 6 months then defaulted next month.

## Model Comparison
In these 3 models, Logistic Regression model has the highest recall but the lowest precision, if the firm expects high recall, then this model is the best candidate. If the balance of recall and precision is the most important metric, then Random Forest is the ideal model. Since Random Forest has slightly lower recall but much higher precision than Logistic Regression, we recommend the Random Forest model. 


## Limitations
1. Best model Random Forest can only detect 51% of default. 
2. Model can only be served as an aid in decision making instead of replacing human decision.
3. Used only 30,000 records and not from US consumers.

## Future Work
1. Models are not exhaustive. Other models could perform better.
2. Get more computational resources to tune XGBoost parameters.
3. Acquire US customer data and more useful features.I.e.customer income.
