# **Commodity Price Prediction using Machine Learning**

This repository contains the code for a machine learning model that can predict the price of a commodity. In this particular project we are predicting the price of laptops given the configuration details. The goal of the project is to build a website wherein the configuration of laptops can be entered and the predicted price for the same is obtained as output.

## **Dataset**
The available dataset is in csv format and has 1303 rows and  12 columns. It includes specification details of different laptops along with its price.

<p align="center">
  <img src="https://github.com/saras56/Commodity_Price_Predictor/assets/115695360/13ee5609-0e5a-4ea4-9ddc-d6bff288c3fd" alt="Description of the image">
</p>
<p align="center">
  Sample dataset
</p>

## **Data Preparation**
Many feature engineering steps have been carried out to clean and process the data.  Only those columns that have a strong correlation with target variable ‘price’ is included in the dataframe. Other columns have been dropped. Thus after processing there are 13 columns in the dataframe. As the original distribution for target variable ‘price’  was left skewed, log transformation was applied to make it normal. As there are many categorical columns, Column transformer was used to apply one hot encoding to the data. The train test split is done in such a way that 85% of the data goes to training and remaining 15% for test.    

## **Model Training and Results**
An sklearn Pipeline was build to train the model where the first step of pipeline is to perform one hot encoding and the second step is training the model. GridsearchCV with shufflespplit was used to perform hyperparameter tuning and choose the best model. R2 score and Mean Absolute Error was used to evaluate the results. Random Forest was chosen as the best model. It showed an R2score of 88.4% and MAE of 0.16.   
 
## **Inference**
A website application to predict the price of the laptop given its configuration details was created using Streamlit.  Later it was deployed on Heroku
This is the Heroku link : https://price-predictor-4676c95e8d7f.herokuapp.com/

![image](https://github.com/saras56/Commodity_Price_Predictor/assets/115695360/62037cf2-ff08-40d3-8557-6998c2513ef0)
![image](https://github.com/saras56/Commodity_Price_Predictor/assets/115695360/9ca5bfa2-2ddd-4ffd-9d49-8e9994c89fa6)

## **Future work**
- Increase the number of samples in the data 
- Try more models like SVM, ExtraTrees,Gradient Boosting Regressor, Ridge Regressor, Voting Regressor, StackingRegressor with different train test ratio and tune the hyperparameters
- Try out feature selection 
