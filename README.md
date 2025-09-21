# Time Series Analysis of Air Pollution Data

## Project Overview

This project performs a time series analysis on air quality data to identify key factors influencing air pollution and forecast future trends of specific pollutants using the Prophet library. The analysis involves data cleaning, handling missing values, exploratory data analysis (including correlation analysis), and time series forecasting.

## Dataset

The dataset used in this project is the [Air Quality UCI Dataset](https://archive.ics.uci.edu/ml/datasets/Air+Quality). It contains hourly measurements of air pollutant concentrations and meteorological parameters from a city in Italy.

## Project Structure

-   `AirQualityUCI.csv`: The raw dataset file.
-   `your_notebook_name.ipynb`: Jupyter notebook containing the code for data loading, cleaning, analysis, and forecasting.
-   `README.md`: This file.

## Analysis Steps

1.  **Data Loading and Initial Inspection**: Load the dataset and perform initial checks on its structure, shape, and missing values.
2.  **Data Cleaning and Preprocessing**: Handle missing values (tagged as -200 in this dataset) by replacing them with NaN and then imputing them (e.g., with the mean). Remove irrelevant columns.
3.  **Feature Engineering**: Combine Date and Time columns into a single datetime column for time series analysis.
4.  **Exploratory Data Analysis**:
    -   Calculate and visualize the correlation matrix to understand the relationships between different air quality parameters and environmental factors.
    -   Identify potentially important factors for predicting air pollution based on correlations.
5.  **Time Series Forecasting with Prophet**:
    -   Select a target air pollutant (e.g., CO(GT)) for forecasting.
    -   Prepare the data in the format required by Prophet (`ds` for datetime, `y` for the target variable).
    -   Initialize and fit the Prophet model.
    -   Generate future dates for forecasting.
    -   Make predictions using the fitted model.
6.  **Visualization of Forecast and Components**: Plot the historical data, forecast, trend, and seasonality components.
7.  **Comparison of Trends**: Compare the forecast trends of different pollutants or environmental factors (e.g., CO(GT) and RH).
8.  **Conclusion**: Summarize the findings from the analysis and forecasting. Discuss the identified essential factors and the predicted future trends.

## Key Findings

-   **Important Factors**: Based on the correlation matrix, **PT08.S1(CO)**, **C6H6(GT)**, **PT08.S2(NMHC)**, and **NOx(GT)** show strong positive correlations with **CO(GT)**, suggesting they are important factors related to Carbon Monoxide levels. **PT08.S3(NOx)** shows a strong negative correlation with **CO(GT)**. Environmental factors like **Temperature (T)**, **Relative Humidity (RH)**, and **Absolute Humidity (AH)** show weaker correlations with CO(GT) but have stronger correlations among themselves and with other pollutants like **PT08.S4(NO2)**.

-   **Trends in Forecast**:
    -   The forecast for **CO(GT)** shows a general decreasing trend over the forecasted period. There are also noticeable daily and weekly seasonality patterns.
    -   The forecast for **Relative Humidity (RH)** shows fluctuations and a general decreasing trend as well, but with different seasonal patterns compared to CO(GT).

-   **Seasonality Patterns**: The Prophet model identified significant daily and weekly seasonality for both CO(GT) and RH, indicating that their levels follow predictable patterns within a day and across a week.

-   **Comparison of Trends**: The comparison plot of the trend lines for CO(GT) and RH indicates that both pollutants show a general downward trend over the period of the data and the forecast, though the magnitude and shape of the decline differ.


## How to Run the Code

1.  Clone this repository.
2.  Ensure you have Jupyter Notebook or JupyterLab installed.
3.  Install the required libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `prophet`. You can install them using pip:
    ```bash
    pip install pandas numpy matplotlib seaborn prophet
    ```
4.  Open the `your_notebook_name.ipynb` file in Jupyter Notebook/Lab.
5.  Run the cells sequentially to execute the analysis.

## Contributing

Feel free to contribute to this project by opening issues or submitting pull requests.
