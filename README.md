# Siemens-Advanta-Consulting-Project

Siemens Advanta is a global consulting and trusted implementation partner for digital and sustainability transformations on an enterprise level.

As part of the course "Business Cases with Data Science" at NOVA IMS, we had the opportunity to work on a Time Series case study using real-world data provided by **Siemens Advanta Consulting**. The case was introduced and guided by two Siemens representatives- **Edward Graf** (Senior Project Manager) and **Hande Gündüz** (Senior Consultant)- who generously shared their insights, answered our questions about the project, and gave us a deeper understanding of their day-to-day work in data-driven consulting. 

Due to the project using real data, we are **unable to share the original datasets or project notebooks**. However, we can provide a high-level overview of the challenge, methodology, tools, and steps followed throughout the case.

## Why is AI-driven sales forecast so important?

Manual forecasting introduces bias, through the "judgement" of several stakeholders. Additionally, manual forecasting is highly-resource intensive, requiring significant time and effort from employees.
To overcome these challenges, **Time Series Forecasting** techniques can be employed as a more efficient and scalable alternative.
A forecast is the development of unknown future information in a certain time horizon, using available information.


## Siemens Advanta Consulting- challenge

The objective of this project was to develop a model capable of forecasting monthly sales for a Siemens Business Unit in Germany, across a range of product lines, with the goal of minimizing RMSE (root mean squared error).

To achieve the final model, we were supplied with a dataset called "Sales data", containing daily sales data, from each product group, from October 2018 until April 2022. Additionally, the sales data was complemented with a secondary dataset refered as "market data", which included key macroeconomic indicators from  Siemens' most important countries. Examples of these macroeconomic variables include:

- Production Index Machinery & Electricals
-  Shipments Index Machinery & Electricals
-  Price of Base Metals
- Price of Energy 
- Price of Metals & Minerals
- Price of Natural gas index
- Price of Crude oil, average 
- Price of Copper
-  Producer Prices

The model's accuracy was evaluated using a sales test dataset covering the period from **May 2022 to February 2023**.

## Solution

This project followed the **CRISP-DM methodology**, providing a structured approach to data mining and analysis. After an initial data inspection, we carried out the following steps:


- Handled **missing values using MICE imputation**. MICE creates interdependencies among variables to better capture underlying patterns, and imputes missing values based on the average of multiple iterations of predictive models.
- Removed highly correlated variables, to **reduce dimensionality**.
-  Merged the sales and market datasets, and performed **outlier detection and removal**, and **addressed anomalies**.  Additionaly, March 2020, which showed a sharp drop due to the onset of COVID-19, was replaced with the average of all other March values to reduce distortion.
-  Tested the data for **stationarity**, a necessary step to determine the suitability of traditional time series models such as ARIMA and SARIMA.

We explored a variety of forecasting models, including:

- ARMA, ARIMA, SARIMA, VAR, Prophet, XGBoost, RNN, LSTM and GRU.

Given the diversity of product groups, model performance varied across group of products. However, for the vast majority of product groups, XGBoost consistently outperformed the other models, achieving the lowest RMSE and demonstrating strong predictive capabilities.

