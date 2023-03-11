# Walmart-TimeSeries-Forecasting

# Capstone Project: Time-series Forecasting of the weekly sales for a retail chain

# 1. Problem Statement

A retail store dataset has been provided which has multiple outlets across the 
country that are facing issues in managing the inventory - to match the demand 
with respect to supply. An analysis of the data must be done along with machine 
learning predictions, in order to provide useful insights and forecast the sales for 
the next 12 weeks.

# 2. Project Objective

The objective of the project is to perform data analysis of the given data and to 
derive useful insights. Further, a time series model can be optimised to forecast
the weekly sales for each store. The above can be performed using SARIMA 
(Seasonal Autoregressive Integrated Moving Average). And hence, the stores can 
improve favourably in various areas based on their sales forecast.

# 3. Data Description 

The walmart dataset used has 6435 rows and 8 columns. The description of the
columns are as follows:

# Feature Name-Description

Store-Store number
Date-Week of Sales
Weekly_Sales-Sales for the given store in that week
Holiday_Flag-If it is a holiday week or not?
Temperature-Temperature on the day of the sale
Fuel_Price-Cost of the fuel in the region
CPI-Consumer Price Index
Unemployment-Unemployment Rate

Here the Date column ranges from 2010-05-02 to 2012-10-26, which is around 
29 months.

# 4. Data Pre-processing Steps and Inspiration 

The dataset was loaded as a dataframe using pandas. The Date column was 
converted into a datetime type and was taken as the index of the dataframe. Also, 
the holiday_Flag column was converted into a category type for convenience. 
The number of null values were checked and were found to be none. 
Further, the unique values of the Store column was observed to be ranging from 
1 to 45. A custom function called store_df was created to obtain the subset of 
dataframe for each store, which on calling, created a dataframe for the sales in a 
particular store.

In the exploratory data analysis phase, the stores with the highest and lowest sales 
were identified to be Store-20 and Store-33 and were analysed individually. 
Further, it was found that the total sales during holidays were lower than that of 
non-holidays and was visualised through a pie chart. The correlation between the 
features was also observed using a heatmap. 

# 5.Choosing the Algorithm for the Project 

The stationarity of the time series was checked using the Augmented Dickey-Fuller test and was found to be stationary. Then, the seasonal decomposition of 
the weekly sales was performed. Further, the data was logarithmically 
differentiated, and autocorrelation plots were made. The SARIMA model was 
chosen to accommodate the dynamic sales data of all stores.

# 6. Motivation and Reasons for Choosing the Algorithm 

The SARIMA algorithm was chosen as there’s a repeating cycle in which the 
sales peaks at the end of the year in the given time series. In such cyclical cases,
SARIMA is significantly more powerful than ARIMA in handling any 
complexities.

# 7. Assumptions 

The following assumptions were made in order to create the model for the project:

• As per the SARIMAX results, the (p,d,q) values were taken as (1,1,1) and 
the seasonal order was taken as (0, 0, 0, 12).

• The residuals have zero mean, constant variance and are also uncorrelated.

# 8. Model Evaluation and Technique

The model evaluation method used was mean squared error which was found to 
be 0.0009. For forecasting, the number of steps was taken as 3 months (required: 
12 weeks), and 95% and 99% confidence intervals were also calculated. Then, 
the forecast for the store was visualised through a line graph.

# 9. Inferences from the Project 

The overall inferences from the data are as follows:

• Total sales during holidays are lower than those during non-holidays.

• There are peaks in sales towards the end of each year.

• The fuel price has negligible correlation to the weekly sales.

• The unemployment rate has a negative correlation with the weekly sales.

• The temperature and CPI have very low negative correlation to the sales.

• Store-20 has the highest total weekly sales. The highest sale in Store 20 
was on 24th December 2010- the week before Christmas: the fuel price 
was less than the mean, the CPI was close to the overall minimum of 203 
for the store and the unemployment rate was in the 75th percentile.

• Store-33 has the lowest total weekly sales. The lowest sale in Store 33 was 
on 12th March 2010: it was not a holiday, the unemployment rate was in 
the 75th percentile and the CPI was low.

• Among the forecasts done for the Stores-1,20 and 33, only Store-33 is 
observed to have a lower sales forecast.

# 10. Future Possibilities 

The future possibilities for this project includes: forecasting for a whole year to 
see if the model can predict the spike in sales towards the end of the year. Also, 
specific forecasting for holidays and non-holidays can be done for each store. 
This can help in managing the inventory for any anticipated spike in demand.

# 11. Conclusion 

This project has succeeded in optimizing a time series model to forecast weekly 
sales for each store. Also, the data analysis has provided with interesting insights 
that can help in decision making by the retail chain. Further, specific feature-dependent forecasting can be done using the model to improve the sales by the 
retail chain.
