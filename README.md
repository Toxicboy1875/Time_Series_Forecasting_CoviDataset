# COVID-19 Time Series Forecasting Using SARIMAX

## Project Overview

This project applies time series forecasting to model and predict daily COVID-19 deaths using the SARIMAX (Seasonal Autoregressive Integrated Moving Average with eXogenous variables) model. The goal is to create an accurate predictive model that helps in understanding patterns and forecasting future trends of COVID-19 fatalities, aiding in policy-making, healthcare preparedness, and resource allocation.

## Dataset

- **Size**: 1,048,575 rows and 21 features
- **Key Features**:
  - `DATE_DIED`: Date of death (used to create time series)
  - `AGE`: Patient's age
  - Health-related attributes: Pneumonia, Diabetes, Obesity, etc.
- **Sample Data**:
  - Includes categorical variables like `SEX`, `ICU`, `PREGNANT`, and other health conditions

## Methodology

1. **Data Cleaning and Preprocessing**
   - Removed duplicates
   - Handled invalid date entries
   - Excluded rows with missing death dates
   - Created a continuous time series of daily death counts

2. **Outlier Detection**
   - Used IQR method to remove outliers in the `AGE` feature

3. **SARIMAX Model**
   - Order: (1, 1, 1) for ARIMA component
   - Seasonal component: (1, 1, 1, 7) for weekly seasonality
   - Training set: 80% of data
   - Testing set: 20% of data

4. **Forecasting**
   - Evaluated using Mean Absolute Error (MAE)
   - Provided confidence intervals for forecasts

5. **Feature Correlation Analysis**
   - Identified significant factors related to death outcomes
   - Generated heatmap for visualizing correlations

## Results

- SARIMAX model performance:
  - MAE: 6.07 (average prediction error of about 6 deaths per day)
  - AIC: 3581.793
- Captured general trend of daily deaths
- Provided reliable short-term forecasts
- Correlation analysis revealed strong relationships between death outcomes and factors like ICU admission, patient type, age, and certain comorbidities

## Conclusion

This project demonstrates the effectiveness of time series modeling for forecasting COVID-19-related deaths. The SARIMAX model successfully captured weekly seasonality and provided insights into daily death trends. The feature analysis highlighted critical health conditions and demographics most associated with fatal COVID-19 outcomes.

The project establishes a foundation for using predictive models in public health decision-making, potentially improving healthcare systems' ability to anticipate and respond to surges in COVID-19 fatalities.

## Future Work

- Refine the model with different SARIMAX orders or additional exogenous variables
- Compare SARIMAX results with other time series models (e.g., Prophet, LSTM)
- Conduct geospatial analysis if location data is available
- Explore feature engineering opportunities to enhance predictive power

---

For more information or to contribute to this project, please contact [Your Contact Information].
