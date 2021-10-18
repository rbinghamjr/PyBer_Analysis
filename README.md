# PyBer_Analysis
## Overview
At the beginning of this analysis, multiple charts and graphs were created to visualize the data for rural, suburban, and urban cities. In this data we were able to determine the average fare per city, along with drivers and rides per city.

Out of the data set we were able to determine the total rides, total drivers, total fares, average fare per ride, and average fare per driver for each city type. Further analysis was needed to create a visualization to show fares during the time frame of January to April 2019 in each city type.

## Results
The first visualization is a data frame showing specific data for each city type. First, we calculated the total rides, the total drivers, total fares, average fares per ride, and average fares per driver.
```
#  1. Get the total rides for each city type
total_rides = pyber_data_df.groupby(["type"]).count()["ride_id"]
# 2. Get the total drivers for each city type
total_drivers = city_data_df.groupby(["type"]).sum()["driver_count"]
#  3. Get the total amount of fares for each city type
total_fares = pyber_data_df.groupby(["type"]).sum()["fare"]
#  4. Get the average fare per ride for each city type. 
average_fare_per_ride = total_fares / total_rides
# 5. Get the average fare per driver for each city type. 
average_fare_per_driver = total_fares / total_drivers
```
Once the code was written then we were able to place into a DataFrame to have a visualization of each city type.

![image](https://user-images.githubusercontent.com/90691846/137819327-2748bf0b-03f9-48af-bb9c-9c4a9bd706f7.png)

In this data we can see some expected outcomes:
  - Rural cities had ~13 times less total rides than urban cities, but the average fare per driver was more than double that of the urban cities
  - Urban cities employed more drivers than actual rides were given.
  - Suburban cities had a better ratio of drivers versus rides.

To further analyze the data, we created a chart showing Total Fare by City Type from January to April 2019.

![image](https://user-images.githubusercontent.com/90691846/137819739-12416681-3bba-4862-b16b-1c5aca7912dd.png)

If we review the data in the chart then we can see the peaks and valleys for each city type almost mirror each other. However there are a few areas of difference.
  - In the beginning of January there was an increase in total fares for suburban and urban cities but a decrease in rural cities. 
  - The highest peak for rural cities was in the beginning of April.
  - All three cities had a spike around Valentine's Day.

## Summary
After reviewing the results above there are some takeways/recommendations that can be made.
  - For each city type there are consecutive peak times when there are more total fares. Driver staffing should be increased to ensure there are ample drivers to meet the demand.
  - There is a large variance of average fare per driver between the three city types. I would suggest to have more drivers for the rural areaas and less drivers in the Urban areas. 
  - By following the peaks and valleys of the chart, I would suggest overall staffing be adjusted to mirror the projected total fares. This will increase the value received for the service being provided during these peak and low times.
