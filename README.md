# Time-Series-Forecasting-Using-XGBoost: Air Quality Index (AQI) Prediction for Kathmandu Valley

## Project Overview

This project aims to forecast the Air Quality Index (AQI) for Kathmandu Valley using historical data from January 2023 to March 2025. The AQI is measured across multiple pollutants including CO, NO, NO₂, O₃, SO₂, PM2.5, PM10, and NH₃. By leveraging machine learning techniques, specifically the XGBoost library with MultiOutputRegressor, this project predicts future AQI values for all pollutants simultaneously.

## Data

The dataset used in this project contains AQI measurements for Kathmandu Valley from January 2023 to March 5, 2025, obtained through the OpenWeather API. The data is fetched within the notebook and stored in the `datasets` folder. The data is structured as a time series, with each row representing multiple AQI values for a specific date.

## Project Structure

This project is implemented as a Jupyter notebook with the following structure:

- Data collection cells that fetch data from OpenWeather API and store it in the `datasets` folder
- Data loading cells that read the stored data for analysis and modeling
- Preprocessing and visualization cells
- Model training and evaluation cells
- Forecasting cells

Additionally, the project includes:
- `aqi_api.py`: External Python file containing the OpenWeather API key configuration
- `datasets/`: Folder containing the stored AQI data files

## Preprocessing

Before training the model, the data went through several preprocessing steps:

1. **Data Cleaning**: Remove unwanted parameters and duplicates, and ensure data consistency.
2. **Feature Engineering**: Create additional features from the existing data, such as day of the week, month, or any other relevant information that could improve the model's performance.
3. **Outlier Detection and Handling**: Two methods are employed to identify outliers in the data:
   - **IQR Method**: Uses the Interquartile Range to identify values falling outside 1.5 × IQR from the first and third quartiles for each pollutant.
   - **Z-score Method**: Identifies data points with Z-scores greater than 3 or less than -3, indicating values more than 3 standard deviations from the mean.
4. **Data Splitting**: The dataset was split into training and testing sets to evaluate the model's performance.

## Visualization

The project utilizes the `seaborn` and `matplotlib` libraries to visualize the data. Various plots and charts are generated to understand the data better and identify any potential correlations or seasonality across the different pollutants.

## Model Training

The core of the project revolves around the XGBoost library, specifically the `MultiOutputRegressor` with `XGBRegressor` as the base estimator. This approach allows for simultaneous prediction of multiple AQI pollutant values (CO, NO, NO₂, O₃, SO₂, PM2.5, PM10, and NH₃). The model is trained on the preprocessed historical AQI data, with the goal of learning the underlying patterns and relationships between the features and the multiple target variables.

## Hyperparameter Tuning

The project implements `GridSearchCV` for hyperparameter tuning, systematically exploring different combinations of XGBoost parameters to find the optimal configuration that minimizes prediction error across all pollutants.

## Evaluation

To evaluate the performance of the trained model, the project employs multiple metrics from the `sklearn` library:

1. **Mean Squared Error (MSE)**: Measures the average of the squares of the errors
2. **R-squared (R²)**: Indicates the proportion of variance in the dependent variable predictable from the independent variables
3. **Mean Absolute Error (MAE)**: Measures the average magnitude of errors without considering their direction

These metrics provide comprehensive insights into the model's accuracy and help assess its suitability for forecasting future AQI values.

## Forecasting

Once the model is trained and evaluated, it is used to forecast the AQI values for future periods across all pollutants.

## Dependencies

- `pandas`: For data manipulation and preprocessing
- `numpy`: For numerical computations
- `seaborn` and `matplotlib`: For data visualization
- `xgboost`: For implementing the XGBoost algorithm
- `sklearn`: For evaluation metrics and other machine learning utilities
- `requests`: For API calls to OpenWeather
- `jupyter`: For running the notebook environment
- `scipy`: For statistical functions including Z-score calculation

## Usage

To run the project, follow these steps:

1. Install the required dependencies by running `pip install pandas numpy seaborn matplotlib xgboost scikit-learn requests jupyter scipy`.
2. Obtain your own OpenWeather API key and add it to the `aqi_api.py` file.
3. Launch Jupyter Notebook by running `jupyter notebook` in your terminal.
4. Open the project's notebook file.
5. Execute the notebook cells sequentially to:
   - Fetch data from the OpenWeather API
   - Store the data in the datasets folder
   - Preprocess the data and handle outliers
   - Train the XGBoost MultiOutputRegressor model
   - Tune hyperparameters with GridSearchCV
   - Evaluate the model's performance
   - Generate forecasts for all pollutants
6. The visualizations and evaluation metrics (MSE, R², MAE) will be displayed inline within the notebook.

## API Configuration

The project uses OpenWeather API to fetch AQI data. You will need to:
1. Register at OpenWeather to obtain your own API key
2. Insert your API key in the `aqi_api.py` file
3. The API fetches data for all pollutants (CO, NO, NO₂, O₃, SO₂, PM2.5, PM10, NH₃)