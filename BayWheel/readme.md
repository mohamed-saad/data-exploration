# Understanding Bikes Trips in California's Bay Area
## by Mohamed M. Saad

## Dataset

In this study, we check the main factors that affects the bike trips. Studying these factors helps in understanding the user needs and distribute bikes over the stations in an efficient way. 

Bay Wheels is a regional public bicycle sharing system in California's San Francisco Bay Area. It is operated by Motivate in a partnership with the Metropolitan Transportation Commission and the Bay Area Air Quality Management District. 

As bikes move between stations, a good understanding of the trips flow will allow to provide better service and allocate (or re-distribute) bikes to stations accoridng to the user needs.

Bay Wheels's trip data for public use under Bay Wheels License Agreement, and I will use it to visualize some of the relationship between its fields.

The data used for this investigation is the collected information for the year 2017. It consists of arround half million trips information. Each trip is anonymized and includes:
- Trip Duration (seconds)
- Start Time and Date
- End Time and Date
- Start Station ID
- Start Station Name
- Start Station Latitude
- Start Station Longitude
- End Station ID
- End Station Name
- End Station Latitude
- End Station Longitude
- Bike ID
- User Type (Subscriber or Customer – “Subscriber” = Member or “Customer” = Casual)

The data structured as
- **Timestamp attributes**: start_time, end_time
- **Geo location attributes**: start_station_latitude, start_station_longitude, end_station_latitude, end_station_longitude
- **Identifiers**: bike_id, start_station_id, start_station_name, end_station_id, end_station_name
- **Interval**: duration_sec
- **Categorical**: user_type

Most of these features are promising and can add a value to the analysis except the low level details such as `bike_id` or `start_station_name`.

Basically, I'm interested in finding relationships with trip on both the spacial domain and the time domain. We can categorize the trips based on its length (implied by the duration) or based on the user tpes. 

As a general assumptions here, I will consider trips with less than 1 hour length as `Short Trip`, and longer than 1 hour as `Long Trip`.

## Summary of Findings

The study of Bar Wheels data reveals the following facts about the trips characterstics
- Most of bikes users at Bay Wheels uses it for short trips to go to work / or get back. This kind of trips is short and usually between 8 to 10 minutes. The peak hours for using bikes is at 8 AM and 5 PM (the start and end time for business days).
- Users tends to use bikes during weekends for long trips, and the weekends trips are 40% less than weekdays. Non members (21% of total users) uses bikes for longer trips than Bay Wheel members (Subscribers).
- There is a balance between the bikes pick-up and drop-off, and stations should have at most 10 spare bikes to fullfill user needs. Euclidean distance between pick-up and drop-off bick is less than 10KM for over 99% of data. Few stations has higher drop-off than pick-up that reaches 30 bikes per day. Locating those stations on map shows that it is stations on the city border may be users takes another transportation means after dropping off the bike.
- Stations are usually distributed over the main roads of the cities, and located on three main areas: San Francisco, Oakland and San Jose area. Stations usually process 500-1000 different bikes. Stations at the city borders encounter larger number of bikes that can reach 3500 different bike.


## References
- Lyft [https://www.lyft.com/bikes/bay-wheels/system-data]
- Wikipedia [https://en.wikipedia.org/wiki/Bay_Wheels]
- Open Street Maps [https://www.openstreetmap.org/]
- Estimate the distance between two points (latitude, longitude) [https://stackoverflow.com/questions/15736995/how-can-i-quickly-estimate-the-distance-between-two-latitude-longitude-points]
- Plotting Geigraohic Data [https://towardsdatascience.com/easy-steps-to-plot-geographic-data-on-a-map-python-11217859a2db]


