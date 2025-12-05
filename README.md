# Tayla Project Portfolio

### Heart Disease Paper


### Video Project 

[<img src="images/projtitle.jpg">](https://youtu.be/qNsJqWcyhRY)

### Result of Canadian Federal Election

### Gas Prices

#### Introduction

Gasoline accounts for almost half of the oil consumption in United States, and it is the
largest single volume refined product sold in the United States (TradingEconomics). The U.S. 
Energy Information Administration uses an unweighted average of the daily gas prices (EIA) to 
calculate weekly, monthly, and annual gas prices. This study uses the weekly New York Harbor 
conventional regular gasoline datasat price in cents per gallon. It includes data from 2000 to 
mid-2010, with a total of 575 observations.

A random sequence of observations {xt} that are recorded in a time ordered fashion are time series. 
The objective of this time series analysis is to see how current gas price trends affect future 
gas prices. Furthermore, this time series analysis will propose a statistical model that explains
the relations of adjacent points in the gas prices that are correlated in time.

![Alt text](images/gas1.png)
Figure 1. 

##### Statistical Methods

Upon inspecting the plot of the gasoline data there is a clear upward trend in the time series
see figure 1. A simple linear regression could be used to estimate the trend. The linear trend
is estimated by xt = -33899.69 +16.98zt + wt where xt is the average expected value of
gasoline for a time in years zt. However, linear regression models do not explain all of the 
important aspects of time series. The lagged relationships through autoregressive, and moving 
average models are better suited for investigating time series. These models combine to form the
autoregressive moving average (ARMA) models. The ARMA model regresses the present outcome xt on 
the past outcomes (xt-l, ..., xt-p) with correlated errors. Times series analysis requires that 
the mean and autocovariance satisfy the conditions of stationarity. 

The clear upward trend of the gas data shows that the series is not stationary see figure 1. 
Differencing the data yields a stationary process such that the first difference eliminates a 
linear trend, the second difference eliminates a quadratic trend, and so on.

![Alt text](images/gas2.png)
Figure 2. 

##### Satifying stationarity 

After taking the first difference of the New York gas data we plot the time series, ACF 
and PACF to check if the conditions of stationarity are met. The ACF does not decay to zero very 
quickly as h increases see figure 2. A slow decay in the ACF to zero indicates that differencing 
is required. After taking the second difference the mean is around zero, and is constant. Also, 
the variance is not drifting as much. As h increases the ACF decays to zero very quickly. Thus,
the second difference has made the gas prices data stationary.

##### Estimating models 

The ARIMA model is a broader form of an ARMA model to include differencing. The data
was differenced twice, so d = 2 for the ARIMA(p,d,q). To choose values for p and q we 
inspect the ACF and the PACF of the doubly diffenced data. The ACF seems to cut off at lag 1 and 
the PACF seems to tail off which suggests an ARIMA(0, 2, 1) process see figure 2. Also, upon 
inspecting the PACF we might think that it cuts off at lag 5 and the ACF tails off which 
would suggest an ARIMA(5, 2, 0)process.

###### Decomposing the time series 

![Alt text](images/gas3.png)
Figure 3. decomposed time series 

From the decomposed time series plot there seems to be a yearly trend, thus a seasonal
ARIMA model may be useful. The multiplicative seasonal ARIMA model contains the usual 
ARMA process and a seasonal component. Upon inspecting the ACF at the seasons it is cut off 
at lag 1s which implies that a season is 52 weeks or a year long. Looking at the PACF at the 
seasons, it is tailing off at lags 1s, 2s, 3s, 4s... Thus, I propose a SMA(1) P = 0 , Q = 1. 
Inspecting the lower lags of the ACF and PACF for the non-seasonal component, the ACF cuts off at
lag 1 and the PACF tails off MA(1) within the seasons so p = 0, q = 1 for the dependence
orders. Thus, I suggest the seasonal model ARIMA(0,1,1,)x(0,1,1)52 for the gas data.

#### Results

##### Estimate of Parameters for the Proposed Models

Applying the ARIMA(0, 2, 1) process, the parameter estimate for theta1 is -1. The 
magnitude of theta is equal to 1 so the older observations have the same influence as the more 
recent observations. This violates invertiblity so this model is not useful. The second proposed
model ARIMA(5,2,0) is an AR(5) process of the form xt = -0.7955xt-1 -0.6043xt-2 -0.3416xt-
3 -0.1995xt-4 -0.1047xt-5 + wt. In this model, xt is forecasted using a linear combination of
past five values of the variable. The third proposed model is the ARIMA(0,1,1)x(0,1,1)52.
The seasonal coefficient is -1.0 for a SMA(1) process, so this model is not meaningful in the
same way that the first model fails in being invertible. In these models xt is second difference
of the estimation for next week’s average gas price in the New York Harbor based on the
previous weekly gas prices.

###### Model Diagnostics and the Significance of the Parameter Estimates

To evaluate the model fits on the data we consider the standardized residuals. The assump-
tion is that the standardized residuals are identically and independently distributed with 0
mean and variance one. We want normality of the residuals which we can check with q-qplot.
The Ljung-Box p-values are useful for testing the independence of the residuals. Where the
null hypothesis is that the residuals are independent thus, obtaining large p-values suggests
that the residuals are independent. I tested all the models and then other models by 

##### Model Selection

There were two models that satisfied all of the assumptions of an ARIMA model. These
models are ARIMA(1, 1, 1)x(1, 1, 2)52 and ARIMA( 2, 1, 2)x(0, 1, 1)52. To select between
these two models we will consider their AIC, AICc, and BIC. These measurements compare
their models predictive error while penalizing model with more parameters. Model 2 that is
ARIMA( 2, 1, 2)x(0, 1, 1)52 minimizes AIC, AICc and BIC so we will choose this model to
predict the gas prices.

##### Forecast and Prediction Intervals
The gas prices for the next ten weeks were forecasted using model2 see figure 7. The next
10 weeks are the 26th week to the 35th week of 2010. The figure 7 includes a 95% and 90%
prediction interval that is a range of plausible values for gas price in these 10 weeks. The
95% prediction interval was calculated results in table 4. Due to the double differencing the
forecasts follow the recent trend in the data. The large and quickly increasing prediction
intervals show that the gas prices could increasing or decreasing at any time.

##### Spectral analysis

A spectral analysis was performed on the gas data to identify the first three predominant
periods. The first three predominant periods are 5.5385, 3.6923, and 2.7692. The confidence
intervals for the dominant periods are given in table 5. From the confidence intervals, the
first peak is not significant as the first periodogram ordinate that is 1300.628 lies in the
confidence intervals of the second and third peak. Tthe second periodogram ordinate that
is 1141.463 lies in the confidence intervals of the first and third peak the significance of
the second peak cannot be established. Also, the third peak is not significant as the third
periodogram ordinate is in the confidence intervals of the first and second peak.

#### Discussion

The New York Harbor conventional regular gasoline weekly spot price may be estimated by
a statistical seasonal ARIMA model. This model has the orders of dependence p = 2, d = 1,
q = 2 , P = 0 , D = 1, Q = 1. Seasonal persistence occurs as the yearly gas prices are nearly
periodic in the weeks of the year. The seasonal ARIMA model may be used to forecast gas
prices in New York. A limitation of the study is that the model is specific to the data from
the gas dataset which contains the average gas prices in the New York Harbor. Thus, this
model is only applicable for forecasting average gas prices in the New York Harbor. Other
regions have various economical and geographical differences which alter the trends in their
gas prices. Therefore, different regions would require different models that are built from
the gas prices in their region. Furthermore, it is unlikely that this seasonal ARIMA model
would be able to accurately capture trends in the next 100 years or so as there are a variety
of factors that can completely alter the trajectory of gas prices such as depression or war.
Hence this model would need to be updated every so often to incorporate recent data for
better prediction.

#### Bibliography

1. EIA. (n.d.) Energy Information Administration - EIA - independent statistics and
analysis. About EIA - U.S. Energy Information Administration (EIA) .U.S.EnergyIn-
formation Administration (EIA). https://www.eia.gov/about/. (Last Accessed: April
17, 2022)
2. Trading Economics. (n.d.) Gasoline2022 data - 2005-2021 historical - 2023 forecast
- price - quote - chart. Gasoline - 2022 Data - 2005-2021 Historical - 2023 Forecast
- Price - Quote - Chart.. https://tradingeconomics.com/commodity/gasoline (Last
Accessed: April 17, 2022)
3. YCharts. (n.d.) US Retail Gas Price. https://ycharts.com/indicators/us_gas_price.
(Last Accessed: April 17, 2022)
