# TimeSeries_Homework

Feel free to skip straight to the [Conclusions](#Conclusions). Otherwise, here is the background on the Python files in this repository.

## Background

The financial departments of large companies often deal with foreign currency transactions while doing international business. As a result, they are always looking for anything that can help them better understand the future direction and risk of various currencies. Hedge funds, too, are keenly interested in anything that will give them a consistent edge in predicting currency movements.

In this assignment, you will test the many time-series tools that you have learned in order to predict future movements in the value of the Japanese yen versus the U.S. dollar.

You will gain proficiency in the following tasks:

1. Time Series Forecasting
2. Linear Regression Modeling

- - -

### Files

Use the following starter code to complete this assignment. 

Note: The starter code shows example calculations and figures to use as a guide. However, your actual output may differ depending on the code and data used.

[Time-Series Starter Notebook](Starter_Code/time_series_analysis.ipynb)

[Linear Regression Starter Notebook](Starter_Code/regression_analysis.ipynb)

[Yen Data CSV File](Starter_Code/yen.csv)

- - -

### Instructions

#### Time-Series Forecasting

In this notebook, you will load historical Dollar-Yen exchange rate futures data and apply time series analysis and modeling to determine whether there is any predictable behavior.

Follow the steps outlined in the time-series starter notebook to complete the following:

1. Decomposition using a Hodrick-Prescott Filter (Decompose the Settle price into trend and noise).
2. Forecasting Returns using an ARMA Model.
3. Forecasting the Settle Price using an ARIMA Model.
4. Forecasting Volatility with GARCH.

#### Linear Regression Forecasting

In this notebook, you will build a Scikit-Learn linear regression model to predict Yen futures ("settle") returns with *lagged* Yen futures returns and categorical calendar seasonal effects (e.g., day-of-week or week-of-year seasonal effects).

Follow the steps outlined in the regression_analysis starter notebook to complete the following:

1. Data Preparation (Creating Returns and Lagged Returns and splitting the data into training and testing data)
2. Fitting a Linear Regression Model.
3. Making predictions using the testing data.
4. Out-of-sample performance.
5. In-sample performance.

### Conclusions

Use the results of the time series analysis and modeling to answer the following questions:

A. Based on your time series analysis, would you buy the yen now?\
B. Is the risk of the yen expected to increase or decrease?\
C. Based on the model evaluation, would you feel confident in using these models for trading?\

1. Ignoring the model accuracy and confidence intervals (not typically a good idea), it would appear a bad time to convert dollars to yen as the yen is forecasted to depreciate in value. In addition the volatility is expected to increase so the error margin might be greater assuming the GARCH model is correct. 
2. The risk of the yen is expected to increase based on the GARCH model forecast from 7.44% volatility to 7.60% volatility over the next five days.
3. None of these models are good enough for trading. The significance is too low as well as the adjusted R^2. It's possible adjusting the lags might improve the results.


Use the results of the linear regression analysis and modeling to answer the following question:

* Does this model perform better or worse on out-of-sample data compared to in-sample data?

Based on the RMSE of the out-of-sample being lower than the in-sample data it would appear that the model is underfitted. Looking at the model itself, the adjusted r squared is very low, which is telling us that the model explains very little (0%) of the changes in the returns. The p-value of the lagged return is not statistically significant. Based on this, I would not use lagged return data of the changes in Yen futures to predict future returns.