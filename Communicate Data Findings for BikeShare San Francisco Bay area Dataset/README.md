# (Communicate Data Findings for BikeShare San Francisco Bay area Dataset)
## by Mohamed Galloul


> **NOTE: Kindly consider taking a look at the uploaded notebook for full analysis and visualization.**


## Dataset

> This data set includes information about individual rides made in a bike-sharing system covering the greater San Francisco Bay area. [source](https://www.bikeshare.com/data/) 

## Cleaning Data
- Drop `NaN`'s values in the dataset since we can't fill them any random values or even fill them with the mean or median, e.g., `NaN`'s in `user_type` and `user_gender`
- convert `start_time` and `end_time` dtype from object to datetime.
- convert `start_station_id`, `end_station_id` and `member_birth_year` dtype from float to int.
- convert `user_type`,`member_gender` and `bike_share_for_all_trip` dtype from plain object to categorical.

### Feature Engineering
Since the traveled distance wasn't provided in the dataset, we can take another approach to calculate the distance between the start and end stations based on their latitude and longitude (doesn't mean it's the ride traveled distance)
<br>
**Note:** such approach is not quite accurate since we don't how the ride track was, however, we will generate this feature to get some sense of the distance between the start and end stations.
<br>
**Note:** '0' indicates that the member returned the bike to the same station where the bike was taken from.

<hr>
 We will extract the start hour and end hour from start time and end time, respectively.

## Summary of Findings

### Univariate Exploration
 - Majority of rides take 630 sec (around 10 min) on average up to 5000 sec
- Majority of the members were born in [1980, 2000] interval with more that 10,000 members were born in 1988 and as we go down from 1980, number of members deceased until we find members who were born in 1878!
- We also found extraordinary rides that distances of more than 10 km in fact they are only 9 rides out of the 174952 rides.
- Majority of members (more than 90%) were subscribed to bike-share service while less than 10% of members weren't subscribed.
- Male members are around 75% of all members while Females are around 23% and 2% of Others.
- Around 90% of members were using bike share for all the trip where the rest of the members used bike share for all the trip.
### Bivariate Exploration
- Majority of trips duration is less than 20000 sec and less 10 km distance (between the start and end station) we can clearly see some trips duration that can extend to more than 80000 sec and there is only 1 trip that had around 70 km distance.
- Members usually tend to return their bike just within the same hour or within the next 3 to 4 hours.
- Since we already know that most of the members were born in [1980, 2000] this heatmap clearly insures that also the heat map shows that majority of members were born in [1985, 1995] specifically.
- We already know that female member tends to have longer trips than male members but what is interesting in the above barplot is despite the gender of the member customers have longer trips than normal subscribers which is unexpected since customers only use the bike service for only 24 hours or 3 days while subscribers have an annual subscription!
- 
## Key Insights for Presentation

- We already know that female member tends to have longer trips than male members but what is interesting in the above barplot is despite the gender of the member customers have longer trips than normal subscribers which is unexpected since customers only use the bike service for only 24 hours or 3 days while subscribers have an annual subscription!
- Customer female members and subscribe male who were born in [1980, 2020] are more likely to have longer trips.

