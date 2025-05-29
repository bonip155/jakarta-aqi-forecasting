# jakarta-aqi-forecasting
Predicting air pollution (AQI) in Jakarta, Indonesia using machine learning based on historical air quality and weather data

## **Overview**
Air pollution is a significant issue in Jakarta, impacting public health and urban living. The goal of this project is to build a **machine learning model** that can **predict future AQI levels** based on historical air quality and weather data. This will help in understanding air pollution trends and potentially assist in urban planning and public health measures.




## Datasets Sources
- [Jakarta AQI Data](https://www.kaggle.com/datasets/senadu34/air-quality-index-in-jakarta-2010-2021)
- [Jakarta Historical Weather Data](https://www.visualcrossing.com/weather-history/Jakarta,%20Indonesia/us/2020-01-01/2020-12-31/)


## Project Structure
- `1_load_and_clean_data.ipynb`  
  Load and clean raw AQI and weather data
- `2_feature_engineering.ipynb`  
  Add lag features, rolling averages, and date/time transformations
- `3_advanced_features.ipynb`  
  Create interaction features, categorize temperature, and classify AQI
- `4_model_training.ipynb`  
  Train Random Forest models for both regression and classification, evaluate with metrics and visualizations


## Machine Learning Task
### Regression
- **Goal**: Predict next day's AQI value
- **Model**: Random Forest Regressor
- **Evaluation**:
  - MAE ≈ 22.5
  - RMSE ≈ 30.3

### Classification
- **Goal**: Predict next day's AQI category (Good, Moderate, Unhealthy, etc.)
- **Model**: Random Forest Classifier
- **Evaluation**:
  - Accuracy ≈ 69%
  - Strong performance on majority class (“Moderate”), weaker on rare categories


## Key Features Used
- Weather: `tempmax`, `humidity`, `windspeed`, `cloudcover`
- Temporal: `month`, `dayofweek`, `is_weekend`
- AQI history: `aqi_lag1`, `rolling_aqi_3`, `aqi_lag3`
- Interactions: `tempmax_x_humidity`, `wind_x_cloud`


## Feature Engineering
Several new features were engineered to improve model performance and capture temporal/environmental patterns:

- **Lag features**: Previous day or previous 3-day values (`aqi_lag1`, `aqi_lag3`, `tempmax_lag1`, etc.)
- **Rolling averages**: Smoothed trends over 3-day windows (`rolling_aqi_3`, `rolling_tempmax_3`)
- **Date-based features**: `month`, `dayof_week`, `is_weekend` to account for seasonal and weekly variations
- **Interaction terms**: Combined features like `tempmax_x_humidity` and `wind_x_cloud` to represent compound effects
- **Categorical encoding**: Converted numerical AQI and temperature into labeled categories (`aqi_category`, `tempmax_category`) for classification

This step significantly enriched the dataset and allowed the models to capture more meaningful patterns.


## Visualizations
- Correlation heatmap
- Actual vs predicted AQI plot
- Feature importance for both regression and classification


### 📄 [Final Report (PDF)](./final_report.pdf)

### Full Report
See the full Jupyter notebook for detailed data cleaning, EDA, model training, and evaluation.
