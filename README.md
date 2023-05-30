# Model Prediction of E-Commerce Shipping Data to Increase On Time Delivery Rate

Final Project Data Science Bootcamp Rakamin Academy Batch 31

## Data
Dataset used in this project is E-Commerce Shipping Data from [Kaggle](https://www.kaggle.com/datasets/prachi13/customer-analytics).

## Background
An e-commerce company is having problem in the high number of late delivery for 59.7% from total delivery. This issue may subsequently caused a decrease in customer satisfaction and also huge loss due to the high churn rate of customer. In order to find the best solution to this problem and increase the on time delivery rate, the company is using machine learning model to predict which delivery will be on time or late.

## Exploratory Data Analysis
- The target feature is **Reached.on.time_Y.N**, it shows that 59.7% of all the products is delayed in delivery.
- **Warehouse block F** keeps the biggest number of products of all warehouse block. But each warehouse blocks show almost equal on time and delay delivery rate.
- Ship is the highest mode of shipment used in delivery, but each mode of shipments show a considerably equal on time and delay delivery rate which is the delay rate is higher than the on time rate.
- Products with low importance category is the highest category with more than 5000 products. The most delayed delivery is the High importance products with 65% delay.
- all products with 2000-4000 grams is late.
- ANOVA analysis shows that **Discount_offered** and **Weight_in_gms** is two best features related to the target feature.

## Data Pre-Processing
- The dataset has no missing values and duplicate data
- Feature Encoding:
    - One Hot Encoding is used for **Warehouse_block** & **Mode_of_Shipment**
    - Label Encoding is used for **Gender** & **Product_importance**
- Log Transformation is used for **Prior_purchases** & **Discount_offered**
- Outliers are removed with Z-score method due to the less data removed by this method.
- Class imbalance : Ratio between the target feature is 60:40, which is still in the normal range.

## Machine Learning Modelling & Evaluation
The target feature contains categorical data (1 and 0), thus the models used are the Classification method of Supervised Learning. The model is used to predict wether the product will be delivered on time (0) or delayed (1). The models are:
- Logistic Regression
- Decision Tree
- K-Nearest Neighbour
- AdaBoost
- XGBoost
- Random Forest

These models is applied for 4 type of data pre-processing to avoid data leakage and to find the best model result. The matrix used is Recall to optimize the False Negative prediction to the very minimum. Based on the result, the best fitted model is Logistic Regression from data with Log Transformation. It shows 76.7% recall in the test set, and 77.4% in the train set, which shows that it is not overfitted nor underfitted significantly.

There are a few recommendation to increase the on time rate of delivery:
- Add other features that are related to the delivery such as: Estimation Time Arrived, Delivery Duration, Type of Product.
- Expand the courier option in peak sales season.
- Periodize the sales discount >10% to avoid overload in delivery.
