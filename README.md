# Tayla Project Portfolio

### Heart Disease Paper


### Video Project 

[<img src="images/projtitle.jpg">](https://youtu.be/qNsJqWcyhRY)

### Result of Canadian Federal Election

### Gas Prices

Introduction

Gasoline accounts for almost half of the oil consumption in United States, and it is the
largest single volume refined product sold in the United States(TradingEconomics). Weekly,
monthly, and annual prices of gasoline are calculated by the U.S. Energy Information Ad-
ministration by taking an unweighted average of the daily prices (EIA). The dataset that is
analyzed in this study contains the weekly New York Harbor conventional regular gasoline
spot price in cents per gallon. This dataset includes data from 2000 to mid-2010, and it has
a total of 575 observations. Understanding the trends in gas prices are indicative of how
the energy industry is performing. Furthermore, a random sequence of observations {xt}
that are recorded in a time ordered fashion are time series. The objective of this time series
analysis is to see how what happened today, and in past days, will affect what happens to-
morrow. Furthermore, this time series analysis will propose a statistical model that explains
the relations of adjacent points in the gas prices that are correlated in time.

![Alt text](images/gas1.png)
Figure 1. 

Statistical Methods

Upon inspecting the plot of the gasoline data there is a clear upward trend in the time series
see figure 1. We might use a simple linear regression to estimate the trend. The linear trend
is estimated by xt = -33899.69 +16.98zt + wt where xt is the average expected value of
gasoline for a time in years zt. However, linear regression models are often unsatisfactory
at explaining all of the important aspects of time series. The lagged relationships through
autoregressive and moving average models are of interest for investigating time series. These
models combine to form the autoregressive moving average (ARMA) models. The ARMA
model regresses the present outcome xt on the past outcomes (xt-l, ..., xt-p) with correlated
errors. To analyze time series data in a statistically meaningful way we require that the
mean and autocovariance satisfy the conditions of stationarity. The clear upward trend
of the gas data shows that the series is not stationary see figure 1. Differencing the data
yields a stationary process such that the first difference eliminates a linear trend, the second
difference eliminates a quadratic trend, and so on.

![Alt text](images/gas2.png)
Figure 2. 

After taking the first difference we plot the time series, ACF and PACF. The ACF does
not decay to zero very quickly as h increases see figure 2. A slow decay in the ACF to zero
indicates that differencing is required. Hence, we take the seocond difference to try to make
the data stationary. Figure 3 shows the second difference of the time series, and its ACF and
PACF. After taking the second difference the mean is around zero and is constant. Also, the
variance is not drifting as much. As h increases the ACF decays to zero very quickly. Thus,
the second difference has made the gas prices data stationary.

The ARIMA model is a broader form of an ARMA model to include differencing. The data
was differenced twice We know that d = 2 for the ARIMA(p,d,q). To choose values for p and q we 
inspect the ACF and the PACF of the doubly diffenced data. The ACF seems to cut off at lag 1 and 
the PACF seems to tail off which suggests an ARIMA(0, 2, 1) process see figure 3. Also, upon 
inspecting the PACF we might think that it cuts off at lag 5 and the ACF tails off which would suggest 
an ARIMA(5, 2, 0)process.

![Alt text](images/gas3.png)
Figure 3. decomposed time series 

From the decomposed plots there seems to be a yearly trend, thus a seasonal ARIMA model
may be useful. The multiplicative seasonal ARIMA model contains the usual ARMA process
and a seasonal component. Upon inspecting the ACF at the seasons it is cut off at lag 1s
which implies that a season is 52 weeks or a year long. Looking at the PACF at the seasons,
it is tailing off at lags 1s, 2s, 3s, 4s... Thus, I propose a SMA(1) P = 0 , Q = 1. Inspecting
the lower lags of the ACF and PACF for the non-seasonal component, the ACF cuts off at
lag 1 and the PACF tails off MA(1) within the seasons so p = 0, q = 1 for the dependence
orders. Thus, I suggest the seasonal model ARIMA(0,1,1,)x(0,1,1)52 for the gas data

Results

Estimate of Parameters for the Proposed Models

Applying the ARIMA(0, 2, 1) process, the parameter estimate for theta1 is -1. The magni-
tude of theta is equal to 1 so the older observations have the same influence as the more re-
cent observations. This violates invertiblity so this model is not useful. The second proposed
model ARIMA(5,2,0) is an AR(5) process of the form xt = -0.7955xt-1 -0.6043xt-2 -0.3416xt-
3 -0.1995xt-4 -0.1047xt-5 + wt. In this model, xt is forecasted using a linear combination of
past five values of the variable. The third proposed model is the ARIMA(0,1,1)x(0,1,1)52.
The seasonal coefficient is -1.0 for a SMA(1) process, so this model is not meaningful in the
same way that the first model fails in being invertible. In these models xt is second difference
of the estimation for next week’s average gas price in the New York Harbor based on the
previous weekly gas prices.
