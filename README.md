# jakarta-aqi-forecasting
Predicting air pollution (AQI) in Jakarta, Indonesia using machine learning based on historical air quality and weather data

## Project Proposal
### **Overview**
Air pollution is a significant issue in Jakarta, impacting public health and urban living. The goal of this project is to build a **machine learning model** that can **predict future AQI levels** based on historical air quality and weather data. This will help in understanding air pollution trends and potentially assist in urban planning and public health measures.




### Datasets Sources
- [Jakarta AQI Data](https://www.kaggle.com/datasets/senadu34/air-quality-index-in-jakarta-2010-2021)
- [Jakarta Historical Weather Data](https://www.visualcrossing.com/weather-history/Jakarta,%20Indonesia/us/2020-01-01/2020-12-31/)


### Process Overview
- Filtered datasets to include only 2020 data.
- Cleaned and standardized date formats.
- Selected relevant columns from the weather dataset and converted temperatures from Fahrenheit to Celsius.
- Merged AQI and weather data on the `date` column.
- Engineered new features: `month`, `dayofweek`, `is_hot_day` (tempmax > 30°C), and `is_polluted_day` (pm10 > 71).
- Visualized correlations between features.
- Split data chronologically into 80% train and 20% test sets.
- Trained a Linear Regression model.


### Results
- **Model:** Linear Regression
- **Features Used:** tempmax, humidity, windspeed, winddir, precip, cloudcover, uvindex
- **Target:** pm10
- **Performance Metrics:**
    - MAE (Mean Absolute Error): ~12.56
    - RMSE (Root Mean Squared Error): ~16.01
    - R² (R-squared): ~-0.92


### Hypothesis Test:
- Question: Does temperature significantly affect PM10?
- Method: Independent t-test comparing hot days vs. non-hot days
- Result: **p-value = 0.0395** -> temperature *does* significantly affect PM10


### Full Report
See the full Jupyter notebook for detailed data cleaning, EDA, model training, evaluation, and statistical testing.
