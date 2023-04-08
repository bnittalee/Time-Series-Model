## New Mexico, Albuquerque: Top 5 zip codes to invest in
<img src="https://github.com/bnittalee/Time-Series-Model/blob/main/Images/ethan-wright-magoon-l0iyYnf5l3w-unsplash.jpg" width="1000">
By Brittney Nitta-Lee

# Business and Data Understanding 
My clients are real estate investors with a focus on properties in King County. Seeking to escape the cold weather, they are interested in exploring investment opportunities in Albuquerque, New Mexico. I will identify five potential zip codes for investment in the area and provide a list of recommendations along with suggested next steps.

# Overview 
The goal of this project is to analyze the historical real estate data for Albuquerque, New Mexico, and identify the top 5 zip codes for investment based on forecasted median home prices. A time series modeling approach is employed to predict future values, helping investors make informed decisions.

## Data Understanding 
In this time series modeling project, I used data from [Zillow](https://www.zillow.com/research/data/). The dataset includes 14,723 rows, each representing a zip code, and 272 columns. The data provides median sales for every zip code from April 1996 to April 2018.

## Zip Code Selection 
Firstly, I filtered the zip codes in the dataset by selecting Albuquerque in the Metro column and then sorted them based on their cumulative Return on Investment (ROI).
<br>For assessing the accuracy of my model, I utilized the root mean squared error (RMSE) to compare it against my baseline naive model. The reason for using RMSE is that it quantifies the differences between predicted and actual values in the same units as the original data, facilitating a straightforward interpretation and comparison of various models.
<br>Lastly, I transformed the data into a monthly time series format to create individual data points for forecasting future home values over the next four years.</br>

## Exploratory Data Analysis 
<img src="https://github.com/bnittalee/Time-Series-Model/blob/main/Images/Median-home-value.png" width="1000">

Once I selected my final 5 zip codees, I created a visualization to see any trends or patterns. To make it easier to analyze and visualize the data, I  resampled the time series to a monthly frequency with the start of each month as the observation point. This aggregated the data for each month and created a new dataframe with the data for the first day of each month. This was particularly useful for forecasting and filling in any gaps in the data.

As you can see, the visualization shows the median home price from April 1996 to Apirl 2018. The trend line has an upward pattern up until 2008 where you can see a downward trend. This is due to the Great Recession. The "Subprime Mortgage Crisis" was a period of time (2007 to 2010) when there was an increase in the number of high-risk mortgages that went into default and caused a ripple effect on the housing market and broader economy. This is important to highlight as I did not inlcuding this data into my modeling.

## SARIMAX Model 

FIn this project, I opted to implement a SARIMAX model as it is well-suited for capturing the seasonality in real estate prices, which tend to exhibit seasonal patterns. This model comprises autoregressive and moving average components and enables us to specify distinct orders for both. Additionally, we can introduce seasonal orders that permit further customization of the model to better align with the data for each zip code. One of the benefits of the SARIMAX model is that it provides interpretable results.
To forecast future home values for the next four years, I utilized the resampled data as a data point.

## Results
