# Time Series Forecasting and Linear Regression Modeling

## Predicting Future Movements in the Value of Japanese yen verse the U.S. dollar

#### Time-Series Forecasting

In this assignment, historical Dollar-Yen exchange rate futures data was used to apply time series analysis and modeling to determine whether there was any predictable behavior.

The data was decomposed using a Hodrick-Prescott Filter into trend and noise 


1. Decomposition using a Hodrick-Prescott Filter (Decompose the Settle price into trend and noise).
2. Forecasting Returns using an ARMA Model.
3. Forecasting the Settle Price using an ARIMA Model.
4. Forecasting Volatility with GARCH.

Use the results of the time series analysis and modeling to answer the following questions:

1. Based on your time series analysis, would you buy the yen now?
2. Is the risk of the yen expected to increase or decrease?
3. Based on the model evaluation, would you feel confident in using these models for trading?

The historical plot of Yen-USD futures settle price indicates a long-term trend of the Yen strengthening against the Dollar and may be a potential long-term investment opportunity. The Hodrick-Prescott Filter decomposed the Settle price into two separate time series of trend and noise. From the Settle verse Trend line plot, the actual Yen settle price significantly fluctuates from the trend line potentially creating short term buying opportunities. As of 10/15, the most recent data in the analysis, the Yen sits below the trend line indicating a potential near-term buying opportunity.

The risk of the yen is expected to increase over the next five days based on the GARCH model. The one-day lag of volatility is statistically significant indicating a relationship between yesterday's volatility to today's volatility in the Settle price. The two-day lag does not show statistical significance.

I would not be confident using the ARMA and ARIMA models, the coefficients have p-values greater than 0.05 and therefore, not statistically significant. Prior days' returns do not appear to be good predictors of future returns. I would be confident in applying the GARCH model in my analysis but would reduce the parameter p to a value of 1.


#### Linear Regression Forecasting

In this notebook, you will build a Scikit-Learn linear regression model to predict Yen futures ("settle") returns with *lagged* Yen futures returns and categorical calendar seasonal effects (e.g., day-of-week or week-of-year seasonal effects).

Follow the steps outlined in the regression_analysis starter notebook to complete the following:

1. Data Preparation (Creating Returns and Lagged Returns and splitting the data into training and testing data)
2. Fitting a Linear Regression Model.
3. Making predictions using the testing data.
4. Out-of-sample performance.
5. In-sample performance.

Use the results of the linear regression analysis and modeling to answer the following question:

* Does this model perform better or worse on out-of-sample data compared to in-sample data?

The linear regression model does a poor job of predicting Yen futures settle returns with lagged Yen futures returns. This is evident by the high deviation between predicted returns verse actual returns from the plot and high root mean squared errors.

The model does perform better on out-of-sample data compared to in-sample data given the lower root mean squared error. This could be due to the smaller data set used in testing and therefore, a lower level of noise. If this test is performed several more times with different time series data selected for training and testing, I would expect the out-of-sample error to be larger than the in-sample error.

Include a Markdown that summarizes your models and findings and include this report in your GitHub repo
