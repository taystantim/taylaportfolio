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

(images/gas1.png)
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


After taking the first difference we plot the time series, ACF and PACF. The ACF does
not decay to zero very quickly as h increases see figure 2. A slow decay in the ACF to zero
indicates that differencing is required. Hence, we take the seocond difference to try to make
the data stationary. Figure 3 shows the second difference of the time series, and its ACF and
PACF. After taking the second difference the mean is around zero and is constant. Also, the
variance is not drifting as much. As h increases the ACF decays to zero very quickly. Thus,
the second difference has made the gas prices data stationary.



