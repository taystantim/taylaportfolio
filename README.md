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

##### Estimating Model Parameters 

Because the data required two differences, we set d = 2 in the ARIMA(p, d, q) model. Examining the ACF 
and PACF of the twice-differenced series, the ACF cuts off at lag 1 and the PACF tails off, suggesting 
an ARIMA(0, 2, 1). Alternatively, the PACF appears to cut off at lag 5 while the ACF tails off, 
suggesting an ARIMA(5, 2, 0).

![Alt text](images/gas3.png)
Figure 3. Decomposed Time Series 

The decomposition indicates a yearly seasonal pattern, implying a seasonal ARIMA may be appropriate. 
The ACF shows a seasonal cutoff at lag 1s (s = 52 weeks), while the PACF tails off at seasonal lags, 
suggesting SMA(1) with P = 0, Q = 1. At non-seasonal lags, the ACF cuts off at 1 and the PACF tails 
off, giving p = 0, q = 1. Thus, a reasonable seasonal model is ARIMA(0, 1, 1) × (0, 1, 1)_{52}.

#### Results

##### Estimate of Parameters for the Proposed Models

For ARIMA(0, 2, 1), the estimate θ₁ = −1 violates invertibility, making the model unsuitable.
The ARIMA(5, 2, 0) model yields:

xₜ = −0.7955xₜ₋₁ − 0.6043xₜ₋₂ − 0.3416xₜ₋₃ − 0.1995xₜ₋₄ − 0.1047xₜ₋₅ + wₜ

Here, the forecast depends on the previous five observations. The seasonal 
ARIMA(0, 1, 1) × (0, 1, 1)_{52} also fails because its seasonal MA(1) coefficient 
is −1, again violating invertibility.

###### Model Diagnostics and the Significance of the Parameter Estimates

Model adequacy was assessed using standardized residuals, q–q plots for normality, and 
Ljung–Box tests for independence. These diagnostics were used to evaluate all proposed 
and alternative models.

##### Model Selection

Two models satisfied ARIMA assumptions:
- ARIMA(1, 1, 1) × (1, 1, 2)_{52}
- ARIMA(2, 1, 2) × (0, 1, 1)_{52}
Using AIC, AICc, and BIC for comparison, ARIMA(2, 1, 2) × (0, 1, 1)_{52} performed best
and was selected for forecasting weekly New York Harbor gas prices.

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
