# CodeClauseInternship_Predicting-House-Prices
## House Price Prediction Using Linear Regression Report

## Table of Contents:


## Introduction
Accurately predicting house prices is a fundamental challenge in the real estate industry. Buyers seek fair pricing, sellers aim to price competitively, and investors depend on sound projections to allocate capital. This project aims to develop a simple yet effective machine learning model that predicts housing prices based on key attributes of a property. By doing so, we explore the power of data-driven insights in real estate decision-making.

## Problem Definition
In the housing market, property prices are influenced by various factors such as size, number of rooms, and furnishing condition. However, identifying how these variables quantitatively impact the final price is not always straightforward. The objective of this project is to build a predictive model that estimates the price of a house using historical data and selected features. The goal is to reduce guesswork and improve pricing accuracy through machine learning.

## Data Source
The dataset used for this project was sourced from [Kaggle](https://www.kaggle.com/datasets/yasserh/housing-prices-dataset). It contains structured data on residential properties, including:

* Area (in square feet)
* Number of bedrooms, bathrooms, and stories
* Availability of mainroad, guestroom, basement, hot water heating, air conditioning
* Furnishing status (furnished, semi-furnished, unfurnished)
* preferred area (prefarea)
* Parking availability
* Price (in INR)
  

## Approach and Methodology

The project followed a systematic process from raw data to model evaluation. The key steps are detailed below:

### 1. Data Exploration

We started by loading and reviewing the dataset to understand the structure, distribution of values, and presence of missing data. This step helped us identify the most relevant features for price prediction.

### 2. Data Cleaning

* **Price Column Cleanup**: The `price` column was originally stored as a string with currency symbols and commas. We removed special characters and converted it to numeric format to make it usable for modeling.
* **Missing Values**: We ensured there were no missing values in the selected features.

### 3. Feature Selection

Based on initial exploration and domain understanding, we selected the following features for the model:

* `area` (square footage)
* `bedrooms`
* `bathrooms`
* `mainroad`
* `stories`
* `guestroom`
* `basement`
* `hotwaterheating`
* `airconditioning`
* `parking`
* `prefarea`
* `furnishingstatus` (categorical)

### 4. Feature Encoding

The `furnishingstatus` column contained categorical values. We applied **One-Hot Encoding** to convert it into numeric form, creating binary columns:

* `furnishingstatus_semi-furnished`
* `furnishingstatus_unfurnished`

The `furnished` category was intentionally dropped to avoid redundancy, as it is implied when both other dummy columns are 0.

### 5. Data Splitting

The dataset was divided into:

* **Training set**: 80% of the data
* **Test set**: 20% of the data

This allowed us to evaluate the model's performance on unseen data.

### 6. Model Training

We trained a **Linear Regression** model using Scikit-learn. This model is based on the assumption of a linear relationship between input features and the target variable (price).

### 7. Model Evaluation

To assess the model’s performance, we used:

* **R² Score**: Indicates how much of the variance in price is explained by the features.
* **Mean Absolute Error (MAE)**: Provides an average of absolute errors in prediction.

## Key Insights and Findings

* **Area** was the strongest predictor of house price.
* **Furnishing status** added meaningful differentiation in pricing — unfurnished and semi-furnished homes generally had lower prices than furnished ones.
* The **bedroom count** showed positive correlation with price, but its effect was smaller than area.
* The final model achieved satisfactory accuracy given the limited feature set, highlighting that even simple models can provide valuable insights when backed by clean, relevant data.

## Conclusion and Recommendations

This project demonstrates that linear regression can be a practical tool for predicting house prices using key property attributes. The model provided interpretable and consistent estimates, validating the effectiveness of thoughtful feature selection and preprocessing.

### Recommendations:

* **Data Enrichment**: Include more detailed features such as location, property age, and nearby amenities for improved prediction.
* **Model Comparison**: Experiment with other algorithms (e.g., Decision Trees, Random Forest) to benchmark performance.
* **Price Segmentation**: Group properties by location or tier to tailor models more precisely.

## Future Work

Going forward, this project can be extended in several ways:

1. **Geospatial Analysis**: Add latitude and longitude data to evaluate the impact of location.
2. **Time Series Component**: Incorporate time-based trends for modeling price appreciation or seasonality.
3. **Dashboard Development**: Build an interactive dashboard for users to input property details and receive a price estimate in real time.
4. **Advanced Modeling**: Apply ensemble models or deep learning techniques to capture non-linear relationships.

