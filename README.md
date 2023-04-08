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

##
