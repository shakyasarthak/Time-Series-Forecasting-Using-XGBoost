# Time-Series-Forecasting-Using-XGBoost: Air Quality Index (AQI) Prediction for Kathmandu Valley

## Project Overview

This project aims to forecast the Air Quality Index (AQI) for Kathmandu Valley using historical data from 2017 to 2021. The AQI is measured in parts per million (ppm) and is a crucial indicator of air pollution levels. By leveraging machine learning techniques, specifically the XGBoost library, this project attempts to predict the AQI values for the year 2022.

## Data

The dataset used in this project contains the AQI measurements for Kathmandu Valley from March 2017 to March 2021. The data is structured as a time series, with each row representing the AQI value for a specific date.

## Preprocessing

Before training the model, the data went through some preprocessing steps:

1. **Data Cleaning**: Remove unwanted parameters and duplicates, and ensure data consistency.
2. **Feature Engineering**: Create additional features from the existing data, such as day of the week, month, or any other relevant information that could improve the model's performance.
3. **Data Splitting**: The dataset was split into training and testing sets to evaluate the model's performance.

## Visualization

The project utilizes the `seaborn` and `matplotlib` libraries to visualize the data. Various plots and charts are generated to understand the data better and identify any potential correlations or seasonality.

## Model Training

The core of the project revolves around the XGBoost library, specifically the `XGBRegressor` module. XGBoost is a powerful gradient boosting algorithm that excels at handling structured and tabular data. The model is trained on the preprocessed historical AQI data, with the goal of learning the underlying patterns and relationships between the features and the target variable (AQI).

## Evaluation

To evaluate the performance of the trained model, the project employs metrics from the `sklearn` library.  Mean Squared Error (MSE) is calculated on the test set. This provide insights into the model's accuracy and help assess its suitability for forecasting future AQI values.

## Forecasting

Once the model is trained and evaluated, it is used to forecast the AQI values for the year upto March 2022.

## Dependencies

- `pandas`: For data manipulation and preprocessing
- `numpy`: For numerical computations
- `seaborn` and `matplotlib`: For data visualization
- `xgboost`: For implementing the XGBoost algorithm
- `sklearn`: For evaluation metrics and other machine learning utilities

## Usage

To run the project, follow these steps:

1. Install the required dependencies by running `pip install pandas numpy seaborn matplotlib xgboost scikit-learn`.
2. Obtain the AQI dataset for Kathmandu Valley from 2017 to 2021 and place it in the project directory.
3. Execute the Python script containing the project code.
4. The script will preprocess the data, train the XGBoost model, evaluate its performance, and generate forecasts for the year 2022.
5. The visualizations and evaluation metrics will be displayed, providing insights into the model's performance and the forecasted AQI values.
