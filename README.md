# Tayla's Projects 

## Retail Trial Analysis – Chip Category

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

This project analyzed historical gasoline prices to understand price trends and forecast short-term future prices. Using weekly New York Harbor gasoline prices from 2000–2010, I built and evaluated time-series models to capture trend, seasonality, and temporal dependence.

### Data
Source: U.S. Energy Information Administration (EIA)
Frequency: Weekly
Metric: Conventional regular gasoline price (cents per gallon)
Observations: 575 data points

### What I Did
- Explored long-term trends and seasonality in gasoline prices
- Transformed non-stationary data using differencing
- Used ACF and PACF plots to guide model selection
- Built and tested multiple ARIMA and Seasonal ARIMA models
- Evaluated models using AIC, AICc, BIC, and residual diagnostics
- Generated 10-week forecasts with prediction intervals

### Methodology
- Identified strong upward trend and yearly seasonality in prices
- Applied second-order differencing to achieve stationarity
- Tested several ARIMA and seasonal ARIMA configurations
= Selected the best-performing model based on fit and assumptions

### Final model selected:
 ARIMA(2, 1, 2) × (0, 1, 1)\₅₂
This model effectively captured both short-term price dynamics and annual seasonal patterns.

### Key Results
- Produced short-term forecasts for gasoline prices in mid-2010
- Forecast uncertainty widened quickly, reflecting volatility in energy markets
- Results highlight the limits of long-range forecasting for commodity prices

### Tools & Skills Demonstrated
- Time series analysis
- ARIMA & Seasonal ARIMA modelling
- Forecasting and uncertainty estimation
- Model diagnostics (residuals, Ljung–Box tests)
- R (data analysis and visualization)

### Why This Project Matters
This project demonstrates my ability to work with real-world time-series data, select appropriate statistical models, and communicate uncertainty

![Alt text](images/gas12.png)


