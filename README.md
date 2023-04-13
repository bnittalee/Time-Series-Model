## New Mexico, Albuquerque: Top 5 zip codes to invest in
<img src="https://github.com/bnittalee/Time-Series-Model/blob/main/Images/ethan-wright-magoon-l0iyYnf5l3w-unsplash.jpg" width="1000">
By Brittney Nitta-Lee
April 11, 2023 

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

For this project, I opted to implement a SARIMAX model as it is well-suited for capturing the seasonality in real estate prices, which tend to exhibit seasonal patterns. This model comprises autoregressive and moving average components and enables us to specify distinct orders for both. Additionally, we can introduce seasonal orders that permit further customization of the model to better align with the data for each zip code. One of the benefits of the SARIMAX model is that it provides interpretable results.
To forecast future home values for the next four years, I utilized the resampled data as a data point.

## Results 
<img src="https://github.com/bnittalee/Time-Series-Model/blob/main/Images/Result_data_frame.png" width="1000">

Each zipcode has the low and high confidence intervals, forecast range, the low end and high end of the forecast range and the ROI. 

The low confidence interval and high confidence interval represent the lower and upper bounds of the range within which the true value of the predicted median home values is expected to fall. Basically, there’s a 95% chance that the true median home value for a given zip code will fall within the range defined by the low and high confidence intervals. 

The low end and high end of the forecast represents the lower and upper bounds, of the predicted range of median home values for a given zip code. These values are calculated using the SARIMAX model and historical data. They represent the range within which the true median home value is expected to fall based on the model’s predictions. 

The forecast range is the difference between the high end and low end values of the predicted range. 

<img src="https://github.com/bnittalee/Time-Series-Model/blob/main/Images/ROI-results.png" width="1000">

## Recommendations 
For those who are interested investing in properties in New Mexico, these are the following zipcodes that has a high return on investment.

1. Corrales, NM (87048)
2. Albuquerque, NM (87106)
3. Santa Ana Pueblo, NM (87043) 
4. Albuquerque, NM (87104)
5. Albuquerque, NM (87122)

The model's inability to generate realistic forecasts resulted in identical forecast ranges for zipcodes 87048, 87106, 87104, and 87122. However, analyzing the ROI paints a different picture. Investors seeking property in New Mexico would be better off considering Corrales (87048) or Santa Ana Pueblo (87043). A 2023 Zillow search revealed that Santa Ana Pueblo's home prices range from  $1,795,950, while Corrales' prices range from $3,800,000. These wide ranges suggest that further investigation of these zipcodes could reveal intriguing insights.

<img src="https://github.com/bnittalee/Time-Series-Model/blob/main/Images/87043.png" width="1000">

The SARIMAX model peformed best on zip code 87043 and provided realistic results. The 95% confidence level is between $375,097 and $441,879. The confidence range is $66,782. Below is the ACF plot for zip code 87043. 

<img src="https://github.com/bnittalee/Time-Series-Model/blob/main/Images/ACF.png" width="1000">

The ACF plot is a bar chart of coefficients of correlation between a time series and it's lagged values. The blue area shows the 95% confidence interval and is an indicator of the significance threshold. Anything within the blue area is statistically close to zero and anything outside the blue are is a statistically close to non-zero. There's a strong correlation at lag 1 and lag 2. There are not many autocorrelations that are significantly non-zero, which is a good indications for a time series model, as it suggests that the model has captured the underlying patterns in the data.

## Next Steps
1. Further investigation into Santa Ana Pueblo and Corrales.
2. Include external factors that may influence real estate prices, such as population growth or unemployment rates.
3. Investigate rapidly growing neighborhoods in New Mexico.

See the full analysis in the [Jupyter Notebook](https://github.com/bnittalee/Time-Series-Model/blob/main/Final-Notebook.ipynb)

For additional info, contact Brittney Nitta-Lee at [bnittalee@gmail.com](mailto:bnittalee@gmail.com)

## Repository Structure

```
├── .ipynb_checkpoints/
├── Data
├── Images
├── PDFS
├── .DS_Store
├── .gitattributes
├── Final-Notebook.ipynb
└── README.md
└── Zillow_data.csv
```
