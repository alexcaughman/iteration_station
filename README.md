
# Iteration Station Project: Does the weather in Atlanta make us crazy in Traffic?

Amber Pizzo,
Alex Caughman,
John Shows,
Steven White

Link to Kaggle dataset used (too large to upload to repo): https://www.kaggle.com/sobhanmoosavi/us-accidents 

# Main Questions to be answered -

## How does precipitation impact traffic incidents in Atlanta?

Using traffic data filtered down to the Atlanta metropolitan statistical area (MSA), accident counts were selected for a group of ten zip codes.  These zip codes reflected the areas with the highest volume of traffic accidents, and therefore, gave us the most data to evaluate in our statistics. Furthermore, as can be seen in Figure 1, these zip codes had over twice the accidents compared to the other zip codes in the Atlanta MSA.

Additionally, we extracted data for a full two-year period (January 2018 through December 2019).  Doing this gave us even more traffic data to evaluate.  When the weather data was added to the analysis it provided a wide variety of weather conditions to evaluate. Increasing the timeframe from one year to two years granted us more weather variation to analyze, as 2018 had significantly more precipitation than 2019. 

(Figure 1:  Accidents_by_Zip_code.png)

![alt text](https://github.com/alexcaughman/iteration_station/blob/master/Images/Accidents_by_Zip_code.png)


Once we had the areas for our analysis determined, we used weather data in conjunction with traffic accidents to make some observations.  

Our initial thought was that precipitation would have a strong relationship with traffic accidents.

Below is a plot evaluating all days within our analysis timeframe: days with precipitation and days without precipitation. 

(Figure 2: Avg_Daily_Accidents_Precip.png)

![alt text](https://github.com/alexcaughman/iteration_station/blob/master/Images/Avg_Daily_Accidents_Precip.png)


As can be seen above, increased precipitation does relate to higher average traffic accident counts.  What about statistically? 

To determine the statistical impact of precipitation, we created box plots of two zip codes that stand out in the chart above.  Zip code 30312 stands out because it appears to show the highest relationship between precipitation and traffic.  Zip code 30324 shows the lowest relationship.

In the first box plot below, zip code 30312 shows that for each increasing precipitation amount, the mean of the traffic accident count goes up.  We also see a large number of outliers.  This is to be expected for the baseline data in particular, as the baseline data was extensive (many more 0 precipitation days than days with precipitation).

In the second box plot, zip code 30324 precipitation shows a noticeably lower relationship with traffic accidents. As precipitation increases, the mean number of traffic incidents appears constant.


(Figure 3 30312_Precip_Boxplot.png and 30324_Precip_Boxplot.png)

![alt text](https://github.com/alexcaughman/iteration_station/blob/master/Images/30312_Precip_Boxplot.png)

![alt text](https://github.com/alexcaughman/iteration_station/blob/master/Images/30324_Precip_Boxplot.png)

So how strong are the relationships?

To answer this, we calculated the correlation coefficient of accidents and precipitation in the same zip codes as above, and found overall that precipitation has a weak positive correlation to number of accidents. This will be explored in the section addressing other weather factors.


## What types of traffic incidents are affected by weather?

Our dataset was somewhat limited in the variation of traffic incident data available.  The dataset did include the number of traffic accidents, as well as a severity index of the traffic accidents.  The severity index did not quantify the accidents in any more meaningful way than just count. We concluded this as most of the data fell into only 2 categories: Severity 2 and Severity 3. However, what these severity levels actually signify was open to some level of interpretation.  Therefore, we used count of accidents per day as our metric for analysis.

We also tried to evaluate interstate accidents vs residential street accidents in our analysis, but due to the volume of traffic carried on our interstate system, interstate crashes vastly outnumbered residential street accidents.

This will be further discussed in the last section of this document.

## What other weather factors play a role in traffic incidents, and how much of a role?

If precipitation has a weak positive correlation, what other weather conditions may affect weather?

In addition to precipitation, our weather data provided maximum temperature, minimum temperature, average temperature, wind chill, snow depth, wind speed, wind gust, cloud cover and relative humidity.  

We chose to further evaluate humidity, temperature, and wind speed because these conditions were continuous and made the most sense given the general conditions in Atlanta.

The correlations of each of these weather conditions to traffic accidents is shown below.

A note on this chart: The precipitation regression analysis was performed on only the precipitation data (days with 0 precipitation were removed and used as “baseline” data). All other parameters were analyzed using the entire dataset.

High Humidity: Above 80%
Low Humidity: Below 80%
High Temperature: above 80 degrees F
Low Temperature: below 80 degrees F
High Wind Speed: above 9mph
Low Wind Speed: below 9mph

(Figure 4 Weather Factor Correlation table)

![alt text](https://github.com/alexcaughman/iteration_station/blob/master/Images/Weather_Factor_Correlation_table.png)



The table shows that precipitation has a positive correlation to accidents, but so does humidity.  Still, both are weak correlations.  It is obvious that weather plays a part in traffic incidents, but not a major part.

We were interested to see if there were any relevant relationships between these variables and accident count.  We did find some interesting results from these evaluations.  As can be seen below (figure 5), precipitation and humidity have similar, albeit weak, correlations.  

(Figure 5: Correlation_Comparison_Precip_Humidity.png)

![alt text](https://github.com/alexcaughman/iteration_station/blob/master/Images/Correlation_Comparison_Humidity_Precipitation.png)

From this chart we can see that many of the zip codes actually see more correlation to humidity than precipitation. However, when looking at average precipitation and average humidity to try to understand this further, we cannot make any meaningful conclusions. It is to be noted that if precipitation was reported in %, we would likely be better able to compare average precipitation and average humidty in a meaningful way, given they would have the same units and share the same right axis.

Also, we wanted to consider whether the heat index in Atlanta had any bearing on traffic accidents.  Unfortunately, we did not have enough data to calculate that metric.

Wind chill was an available variable in our dataset but there were too few data points to give any confidence in the results.


## Do specific locations in Atlanta see higher correlation of traffic accidents to precipitation? 

Yes as seen in figure 4.

## If so, why?

The accidents occurring in the zip codes we selected are primarily on interstate highways.  See figure below:



(Figure 6 Zip_code_Precip_Accidents_Heat_map.png)

![alt text](https://github.com/alexcaughman/iteration_station/blob/master/Images/Zip_code_Precip_Accidents_Heat_map.png)

We chose the zip codes with the highest accident counts, and here we can see our data is heavily skewed to interstate connections and bottlenecks.

There is so much volume of traffic on interstates that it does make sense that more accidents occur on our interstate arteries. 

When we looked at interstate correlation with precipitation, we confirm again that precipitation does play a role in accident counts.

(Figure 7 Accident_Avg_Interstate_Comparison.png)

![alt text](https://github.com/alexcaughman/iteration_station/blob/master/Images/Accident_Avg_Interstate_Comparison.png)


## Our findings: 
Yes, precipitaion plays a role in traffic accidents, but not as significantly as expected. All the weather factors we evaluated pointed to fairly weak correlations. However, any correlation is meaningful, as it will only serve to instigate more accidents on already congested roads.


