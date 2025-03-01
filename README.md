# 1. Natural Gas Price Forecasting and Contract Valuation

## Project Overview

This project focuses on forecasting natural gas prices and valuing storage contracts using time series analysis and bilinear regression. It leverages historical price data to predict future prices and simulates storage contract scenarios to estimate their profitability.

## Methodology

### Time Series Analysis
- **Decomposition:** The time series data is decomposed into trend, seasonality, and residual components using STL decomposition.
- **Stationarity:** Stationarity is checked using the Augmented Dickey-Fuller test, and differencing is applied to make the data stationary if necessary.
- **ARIMA Modeling:** An ARIMA model is fitted to the stationary data to capture autocorrelations and forecast future prices.

### Bilinear Regression
- **Trend:** A simple linear regression model is used to capture the overall trend in prices.
- **Seasonality:** Intra-year variation is modeled using a sine function, fitted using bilinear regression.
- **Interpolation:** An interpolation function is defined to estimate prices for any given date, based on the trend and seasonality components.

### Contract Valuation
- Two methods are provided to calculate contract price.
   - Method 1: Less optimized, calculates the contract price based on forecasted injection and withdrawal prices and associated costs.
   - Method 2: More optimized, calculates the contract price by simulating gas injection and withdrawal on given dates, factoring in costs and revenue.

## Results
The project demonstrates the effectiveness of time series analysis and bilinear regression in forecasting natural gas prices and valuing storage contracts. The generated forecasts can be used to make informed decisions about gas storage and trading.

## Further Development
- **Optimization:** Explore more advanced time series models and optimization techniques to improve forecast accuracy.
- **Real-time Data:** Integrate real-time price data to enhance the accuracy and relevance of the contract valuation model.
- **Risk Management:** Incorporate risk factors and uncertainty into the valuation model to assess potential contract risks.


# 2.Credit Risk Analysis

## Project Overview
This project focuses on analyzing credit risk using machine learning models. The primary goal is to predict the probability of default for loan applicants and estimate the expected loss associated with each loan. The project utilizes various classification algorithms, including Random Forest, Decision Tree, Gradient Boosting, and XGBoost, to achieve these objectives.

## Methodology
1. **Data Preprocessing:** The dataset is loaded, and features are preprocessed using standardization to ensure consistent scaling.
2. **Model Training:** Several classification models are trained on the preprocessed data, including Random Forest, Decision Tree, Gradient Boosting, and XGBoost.
3. **Model Evaluation:** The models are evaluated using the ROC-AUC score and cross-validation to assess their performance and robustness.
4. **Expected Loss Calculation:** A function is defined to calculate the expected loss for each loan based on the predicted probability of default, loan amount, and recovery rate.
5. **FICO Score Quantization:** FICO scores are categorized into different risk levels (Poor, Fair, Good, Very good, Excellent) for further analysis.
6. **Probability of Default Prediction:** The probability of default is predicted for each loan applicant using the trained XGBoost model.
7. **Credit Rating Assignment:** Loan applicants are assigned credit ratings (A, B, C, D, E) based on their predicted probability of default and FICO score category using dynamic programming.

## Results
The XGBoost model exhibited the best performance in terms of ROC-AUC score and cross-validation results. The expected loss for each loan was calculated and assigned to the corresponding loan applicant. Credit ratings were assigned to loan applicants based on their predicted probability of default and FICO score category.

## Usage
1. Load the loan dataset.
2. Preprocess the data using standardization.
3. Train the XGBoost model on the preprocessed data.
4. Predict the probability of default for new loan applicants using the trained model.
5. Calculate the expected loss for each loan.
6. Quantize FICO scores into risk categories.
7. Assign credit ratings based on the predicted probability of default and FICO score category.

## Conclusion
This project demonstrates the application of machine learning models for credit risk analysis. The XGBoost model effectively predicts the probability of default and estimates the expected loss, enabling informed credit risk assessment. The assigned credit ratings provide a comprehensive risk profile for each loan applicant.
