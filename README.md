# Retail Rhythms: U.S. Retail Sales Time Series Forecasting

## About This Project

For this project, I analyzed monthly U.S. retail trade and food services sales to see what past sales patterns can tell us about future consumer spending.

I focused on two main questions:

1. What do historical retail sales patterns reveal about future consumer spending trends in the United States?
2. Can time series models identify the trend and seasonality behind U.S. retail sales?

The data came from the **Federal Reserve Economic Data (FRED)** database and includes monthly retail sales observations from **2010 through 2019**.

## Data

* **Source:** Federal Reserve Economic Data (FRED)
* **Series:** Retail and Food Services Sales (RSAFS)
* **Frequency:** Monthly
* **Years:** 2010–2019
* The final **24 observations** were used as the testing set.
* The remaining observations were used to train the models.

Source: https://fred.stlouisfed.org/series/RSAFS

## What I Did

I started by exploring the data and looking for trends, seasonality, and other patterns.

Some of the methods I used were:

* Time series plots
* Decomposition plots
* Histograms
* ACF plots
* PACF plots
* Box-Cox transformation
* First differencing
* Seasonal differencing
* ARIMA modeling
* Forecasting and model comparison

I also used several residual diagnostic tests to check whether the models were appropriate, including:

* Shapiro-Wilk test
* Box-Pierce test
* Ljung-Box test
* McLeod-Li test

## Model Selection

I tested five different ARIMA models.

At first, the ACF and PACF plots suggested that a simple **ARIMA(0,1,0)** random walk model could be a good option. However, after comparing the models using AICc values and looking at their forecasting results, **ARIMA(1,1,1)** performed the best overall.

### Final Model

**ARIMA(1,1,1)**

* **AICc:** 1764.059
* Had the lowest AICc out of the models tested
* All 24 test observations fell within the forecast intervals
* First differencing was enough to make the series stationary
* A seasonal ARIMA model was not needed

The final model was:

[
(1-0.9999B)(1-B)Y_t=(1-0.9913B)\epsilon_t
]

## Main Findings

The data showed a clear upward trend in retail trade and food services sales throughout the time period I studied.

The project also showed that historical sales data can be useful when trying to forecast future consumer spending. While there was some seasonality in the data, seasonal differencing was not necessary for the final model.

Overall, **ARIMA(1,1,1)** gave the best results based on the model comparison and forecasting methods I used.

## Repository Files

* `Karla Hernandez-174 final project.qmd` — Full analysis and code
* `RSAFS.csv` — Dataset used for the project
* `Retail_Rhythms_Report.pdf` — Final project report
* `Time Series- Retail Rhythms.Rproj` — RStudio project file

## Tools Used

* R
* RStudio
* Quarto
* ARIMA models
* Time series forecasting
* Statistical diagnostic testing
* FRED data

## Full Report

The full report with the analysis, graphs, model comparisons, and forecasting results is included in this repository as a PDF.

## Acknowledgments

This project was completed for a university time series course. Professor Raya Feldman and TA Minxing helped guide me throughout the project, especially when interpreting results and deciding which forecasting model was the best fit.
