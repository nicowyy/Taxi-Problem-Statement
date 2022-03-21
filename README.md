# **Taxi Analysis**
* By: Nico Wee
    * [Tableau](https://public.tableau.com/app/profile/nicowyy)

**Main Goal**

The primary aim of this analysis is to provide an insight into the patterns and trend of yellow taxi trips in the year 2020 and also provide conclusions and recommendations for a fictional business wanting to penetrate into a new market. This documentation is to provide the reader with information about my thought process throughout this project when uncovering and visualizing the dataset.

# Problem Statement

You are a taxi company looking to start your business in New York City but have no knowledge of customers’ ride-hailing patterns. Create a story to show the trend of ride-hailing trend over the year of 2020, analysis based on data shown, conclusions and recommendations.

## Prologue - Gathering Data
The dataset that I will be using will be 2020's [TLC Taxi Record Data](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page).

Before starting on this project, I wanted to use 2021's data in order to provide a more up-to-date taxi trips data but TLC have not fully publicize all of 2021's taxi data as of writing. As such, I will be using the dataset from 2020 to get the next best updated dataset. 
As there are many different kinds of taxi data that TLC has provided, I decided to focus on the yellow taxi data for my analysis. 

A [data dictionary](https://www1.nyc.gov/assets/tlc/downloads/pdf/data_dictionary_trip_records_yellow.pdf) was also used for this project in order to find out what do the IDs mean in the table. Then, I created a seperate Excel file, Payment type, as a table in order to join it to the main table later in Tableau.
I also downloaded a list of taxi zones from [NYC OpenData](https://data.cityofnewyork.us/Transportation/NYC-Taxi-Zones/d3c5-ddgc) which labels all the zones according to their IDs which I will be using it to join in Tableau as well.
As I wanted to show one of the charts in a map, I downloaded a [NYC Taxi Zone in 2016](https://maps.princeton.edu/catalog/nyu-2451-36743) .shp file to be used later.
## First Step - Data Cleaning 
As the Excel files were too big to load its data efficiently, I had to only keep columns that were important to the analysis. I removed VendorID, RatecodeID, store_and_fwd_flag, mta_tax,fare_amount,extra, tip_amount,tolls_amount,improvement_surcharge and congestion_surcharge. I also partially removed payment_type and only kept Cash and Credit Card (1 and 2 in cell value) in order to focus more on those 2 payments. 

I also added in a new column, time_taken, which subtracts the pickup time from dropoff time and change the format into x hr y mins in order to find out how long each trip takes. This allows me to group the trip timings which will be used for analysis. 

For **passenger_count**, 
I filtered and deleted rows that has <1 and 6< passengers as well as null values. For **PULocationID** and **DOLocationID** I deleted rows that have 264 and 265 in the cell values as there are no information or records of location 264 and 265. Then, I filtered time_taken and deleted trip entries that are 4 hours or longer. My reasoning is that 4 hours should be more than enough time to get around from one location to another in NYC. I also deleted entries that have 0 minutes as time_taken which would be inaccurate to the analysis. For **trip_distance**, I deleted entries that seems impossible to be true, for example, an entry with a trip distance of 12000 miles in 2 hours. I also deleted entries that have 0 miles in trip_distance as I will not be including stationary taxi entries in this analysis.

With those parameters in mind, I subsequently cleaned the data for the remaining datasets as well.

## Second Step - Tableau
I 
then 
pulled all the data into tableau and union all 12 months of data into one table and start visualizing them into charts which allows the reader to understand the data pattern. Due to the large amount of data and filesize required of this combined datasets, I could not save my work onto Tableau Public and had to do the story using MS Powerpoint. As such, I will publish all my presentation slides and files in this documentation but I will be unable to upload the tableau file onto GitHub as well due to the 25MB limit.

## Third Step - Presentation
![image](https://user-images.githubusercontent.com/101384168/159224391-f38f47bc-e5d6-4ac4-9fc5-d1ec749d4616.png)
![image](https://user-images.githubusercontent.com/101384168/159224507-df6bda5c-d458-4ecd-8afe-b7aa327b3afe.png)
![image](https://user-images.githubusercontent.com/101384168/159224581-e10912ee-5713-48ec-972a-bb92686898a2.png)
![image](https://user-images.githubusercontent.com/101384168/159224611-e918b459-1d79-4993-870e-f136c1dba20c.png)

## Final Step - Dashboard
I also included a simple dashboard at the end to filter relevant data in order to see different viewpoints of the dataset.

![image](https://user-images.githubusercontent.com/101384168/159227850-ad6f36d1-a811-4017-82b8-edc3f49f8546.png)

## Epilogue - Conclusion and Limitations
With these insights we can show what are the trends of taxi trips monthly and are able to give recommendations based on the data shown. Therefore, the taxi company is able to make a better data-driven decision to penetrate the ride-hailing market in New York City. There are a few limitations regarding this analysis and the data used. As there were multiple null values and false entries in the dataset, accuracy of the data is compromised. TLC's website have also stated that it is difficult to confirm the accuracy of the data. Another limitation would be that as the data used contains millions of rows, I am unable to add in more data like I wanted to, for example, including all data from the past 5 years to do a pattern analysis using the same metrics. 
Data entries for April in this analysis is also questionable as there were significantly lesser entries for April compared to the other months. This could potentially hinder the accuracy of the analysis as well. 

## Contact Me 
Feel free to contact me to give your opinions and feedback regarding this analysis! I will take into account all feedbacks and review past projects I have done to further improve on my next one!
