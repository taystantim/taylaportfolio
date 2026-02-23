# Tayla's Projects 

## Retail Trial Analysis – Chip Category

### Business Question

Did a store-level chip trial generate a true performance uplift, and which customer segments drive category growth?

### Context

Using transaction-level and customer segmentation data, I evaluated purchasing behaviour and measured trial performance against carefully selected control stores. The analysis was completed entirely in Excel to simulate a real-world retail analytics workflow.

### Approach
- Cleaned and merged transaction + customer datasets
- Identified key customer segments (life stage × affluence)
- Selected comparable control stores using historical sales trends
- Measured uplift using scaled comparisons and confidence intervals
  
### Sales Contribution by Customer Segment

Mainstream and Budget families contributed the majority of chip sales, indicating trial success would depend heavily on family-dense store demographics.

### Trial vs Control Comparison

Statistically significant uplift observed in Store X (confidence interval excluded zero), suggesting genuine performance improvement rather than random variation

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


## Video: Selecting the Best Predictor for the Median Housing Value of Calfornia Homes 

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

![Alt text](images/election4.png)
The plot is another pie graph that showcases the conservative support by province. Provinces with
more people have a larger weight in the pie.


## Forecasting New York Harbor Gas Prices

### Project Overview

This project analyzes weekly New York Harbor gasoline prices (1986–2026) using time series modeling and volatility analysis. The objective was to model long-term price dynamics, evaluate forecast performance, and investigate volatility clustering using GARCH methods.

### The analysis combines:
- ARIMA modeling for price forecasting
- Out-of-sample validation
- Volatility modeling (ARCH/GARCH)
- Interpretation of volatility persistence

### Objective
- Determine whether gas prices are stationary
- Identify appropriate ARIMA(p,d,q) structure
- Evaluate forecast accuracy using rolling validation
- Detect volatility clustering
- Model conditional variance using GARCH(1,1)

### Data
- Weekly gasoline prices ($/gallon)
- Time period: 1986–2026
- Frequency: Weekly (ts/xts format)

### Methodology
1️. Transformation & Stationarity
- Applied log transformation to stabilize variance
- Conducted Augmented Dickey-Fuller (ADF) test
- First differencing achieved stationarity (p-value < 0.01)

2. Using ACF and PACF diagnostics:
ACF: gradual decay
PACF: significant early lags

Selected model:ARIMA(4,1,1)

Model diagnostics:
Residual autocorrelation ≈ 0
AICc minimized
No significant remaining structure in residuals

3. Out-of-Sample Validation
- Split data into training and testing sets
- Performed rolling one-step-ahead forecasting
- Compared forecast error metrics (RMSE, MAE)
- Rolling RMSE ≈ 0.0469
- This indicates strong short-term predictive performance.

4. Volatility Analysis
Visual inspection of returns showed volatility clustering — periods of high volatility followed by high volatility.
Squared returns plot confirmed clustering behavior.

5. Fitted GARCH(1,1) to model conditional variance:
Findings:
α + β close to 1 → strong volatility persistence
Half-life ≈ 8 weeks
Interpretation:
Volatility shocks decay gradually and remain impactful for approximately two months

### Forecast Visualization
The model produces:
Point forecasts
95% confidence intervals
Back-transformed price predictions
Forecast intervals widen over time, reflecting increasing uncertainty

### Key Insights
- Gas prices follow a non-stationary process but become stationary after differencing.
- ARIMA(4,1,1) effectively captures mean dynamics.
- Volatility clustering is present and statistically significant.
- GARCH modeling improves understanding of conditional risk.
- Volatility persistence suggests sustained periods of market instability.

### Tools & Libraries
- R
- forecast
- tseries
- rugarch
- xts / zoo
- ggplot2

### Why This Project Matters
This project demonstrates my ability to work with real-world time-series data, select appropriate statistical models, and communicate uncertainty

![Alt text](images/gas12.png)


