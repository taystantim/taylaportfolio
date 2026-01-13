# Tayla's Projects 

## Retail Trial Analysis – Chip Category (Excel)

### Project Summary

In this project, I analysed supermarket transaction and customer data to understand chip purchasing behaviour and evaluate the impact of a store-level trial. The goal was to identify which customer groups drive chip sales and determine whether the trial led to a real improvement in performance. The analysis was completed entirely in Microsoft Excel, demonstrating my ability to clean data, perform analysis, and communicate insights clearly without relying on advanced programming tools.

### What I Did

- Cleaned and prepared transaction and customer datasets
- Merged datasets using Excel formulas and lookups
- Analysed chip sales by customer life stage and affluence
- Built pivot tables to summarise sales, volume, and purchasing behaviour
- Selected appropriate control stores by comparing historical sales patterns
- Compared trial stores against scaled control stores
- Calculated percentage differences and confidence intervals to assess trial impact
- Created charts and a client-ready presentation to communicate findings

### Key Findings

- Mainstream and Budget families accounted for the largest share of chip sales
- Budget customers purchased chips more frequently but at lower price points
- Premium customers contributed a smaller proportion of total sales
- The trial resulted in a statistically significant uplift in some stores, suggesting a genuine performance improvement rather than random variation

### Recommendations

- Roll out the trial selectively to stores with similar customer profiles
- Focus expansion on stores most comparable to the strongest-performing trial store
- Use further trials to test pricing or promotional strategies
- Continue monitoring performance to ensure consistent execution

### Tools & Skills Demonstrated

- Microsoft Excel (pivot tables, formulas, charts)
- Data cleaning and validation
- Customer segmentation analysis
- Trial evaluation and basic statistical analysis
- Data visualisation and storytelling
  
### Why This Project Matters

This project demonstrates my ability to take raw data, turn it into meaningful insights, and communicate results in a way that supports business decision-making.


## Video Project: Selecting the Best Predictor for the Median Housing Value of Calfornia Homes 

[<img src="images/calproj.png">](https://youtu.be/qNsJqWcyhRY)

## Predicting Conservative Vote Share – Canadian Federal Election

### Project Overview

This project used Canadian election and census data to estimate the proportion of voters expected to support the Conservative Party in the next federal election. The goal was to apply statistical modelling and demographic weighting to produce a population-level prediction.

### Data Used

2019 Canadian Election Study (CES) – voter demographics and party preference
2017 General Social Survey (GSS) – population demographics for weighting

### What I Did

- Cleaned and prepared large survey and census datasets
- Filtered and recoded demographic variables for consistency
- Engineered key variables including age, gender, and conservative support
- Built a logistic regression model to predict likelihood of voting Conservative
- Applied post-stratification weighting by province to scale predictions to the national population
- Visualised demographic and regional patterns in voting behaviour

### Methodology

- Modelled Conservative support as a binary outcome using logistic regression
- Used age and gender as predictors based on observed voting trends
- Adjusted estimates using population weights to reflect real demographic distributions
- Aggregated weighted probabilities to estimate national vote share
  
### Key Result
- Estimated 34.7% Conservative vote share, assuming demographic patterns remain consistent
- Found that province population size heavily influences national outcomes
- Identified clear demographic trends in political support by age and gender

### Tools & Skills Demonstrated
- R (data cleaning, modelling, visualisation)
- Logistic regression
- Survey data analysis
- Post-stratification & weighting
- Statistical reasoning and interpretation

### Why This Project Matters
This project demonstrates my ability to work with real-world survey data, apply statistical models, and translate complex analysis into meaningful, population-level insights — core skills for a junior data analyst.

#### Distribution of the data 

![Alt text](images/election1.png)
The plot depicts the frequencies of people in the census data by province. Ontario and Quebec
will have the greatest influence on the proportion of conservative votes. 

![Alt text](images/election2.png)
The plot depicts the relationship between gender and conservative political beliefs. The bar graph shows
the frequency of males and females the survey data set. 

![Alt text](images/election3.png)
The pie graph that illustrates the proportion of people who voted conservative
by the total number of conservative votes by age group. The age group 85-100 has the smallest number
of conservative and this is likely because this age group made up the smallest proportion of people in the
survey (there are only 35 people in this age group). 

![Alt text](images/election4.png)
The plot is another pie graph that showcases the conservative support by province. Provinces with
more people have a larger weight in the pie.



![Alt text](images/election5.png)



## University Paper: Forecasting New York Harbor Gas Prices

### Introduction

Gasoline makes up nearly half of U.S. oil consumption and is the largest refined product sold 
domestically (TradingEconomics). The U.S. Energy Information Administration (EIA) reports 
weekly, monthly, and annual gas prices using an unweighted average of daily prices. This study 
analyzes the weekly New York Harbor conventional regular gasoline dataset (in cents per gallon), 
covering 2000 to mid-2010 with 575 observations.

A time series is a sequence of observations recorded in time order. The goal of this analysis is to examine how current gas price trends influence future prices and to develop a statistical model that captures the temporal dependence between observations.

![Alt text](images/gas1.png)
Figure 1. 

### Statistical Methods

The plot of the gasoline data (Figure 1) shows a strong upward trend. Although a simple 
linear regression, xₜ = −33899.69 + 16.98zₜ + wₜ,can estimate this trend, it does not
capture the key time-dependent structure. Autoregressive and moving-average components, 
combined in ARMA models, are better suited because they model relationships between current and 
past values. The ARMA model regresses the present outcome xt on the past outcomes 
(xt-l, ..., xt-p) with correlated errors.  

The clear upward trend of the gas data shows that the series is not stationary. 
Differencing the data yields a stationary process such that the first difference eliminates a 
linear trend, the second difference eliminates a quadratic trend, and so on.

![Alt text](images/gas2.png)
Figure 2. 

#### Satisfying Stationarity 

After taking the first difference of gas data, the next step was to assess if the series is stationary.
The ACF decayed slowly (Figure 2), indicating that additional differencing was needed. After 
taking the second difference, the series had a stable mean near zero, relatively constant variance, 
and an ACF that decayed quickly. Thus, the second difference has made the gas prices data stationary.

#### Estimating Model Parameters 

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

### Results

#### Model Selection

For ARIMA(0, 2, 1), the estimate θ₁ = −1 violates invertibility, making the 
model unsuitable.

The ARIMA(5, 2, 0) model yields:
xₜ = −0.7955xₜ₋₁ − 0.6043xₜ₋₂ − 0.3416xₜ₋₃ − 0.1995xₜ₋₄ − 0.1047xₜ₋₅ + wₜ
Here, the forecast depends on the previous five observations. 

The seasonal ARIMA(0, 1, 1) × (0, 1, 1)_{52} also fails because its seasonal 
MA(1) coefficient is −1, again violating invertibility.

<img src="images/gas4.jpg" height="300">

Other seasonal ARIMA models were tested on the gas data by altering one dependence at a 
time and then checking if they satisfied the model assumptions. In both of the seasonal 
models ARIMA(1, 1, 1)x(1, 1, 2)52 and ARIMA( 2, 1, 2)x(0, 1, 1)52, all of the coefficients 
or were significant. 

<img src="images/gas5.png" height="300">

Model adequacy was assessed using standardized residuals, q–q plots for normality, and 
Ljung–Box tests for independence. These diagnostics were used to evaluate all proposed 
and alternative models.

![Alt text](images/gas6.png) 
![Alt text](images/gas7.png)

Two models satisfied ARIMA assumptions:
- ARIMA(1, 1, 1) × (1, 1, 2)_{52}
- ARIMA(2, 1, 2) × (0, 1, 1)_{52}

Using AIC, AICc, and BIC for comparison, ARIMA(2, 1, 2) × (0, 1, 1)_{52} performed best
and was selected for forecasting weekly New York Harbor gas prices.

<img src="images/gas10.png" height="100">

#### Forecast and Prediction Intervals

The gas prices for the next ten weeks were forecasted using the seasonal ARIMA model. The next
10 weeks are the 26th week to the 35th week of 2010. The figure 7 includes a 95% and 90%
prediction interval that is a range of plausible values for gas price in these 10 weeks. The large 
and quickly increasing prediction intervals show that the gas prices could increasing or
decreasing at any time.

![Alt text](images/gas12.png)

### Discussion

The New York Harbor conventional regular gasoline weekly spot price can be modeled a seasonal ARIMA:
ARIMA(2, 1, 2) × (0, 1, 1)_{52}. Seasonal persistence occurs as the yearly gas prices are nearly
periodic in the weeks of the year. This model is suitable for forecasting gas prices in this
specific region, but its applicability is limited: other regions have different economic and 
geographic factors that shape price dynamics. Long-term forecasts are also unreliable, as future 
structural changes (e.g., recessions, geopolitical events) could drastically alter price behavior.
Periodic model updates with recent data are therefore necessary for maintaining predictive accuracy.

### Bibliography

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

All analysis for this report was programmed using R version 4.0.2.
