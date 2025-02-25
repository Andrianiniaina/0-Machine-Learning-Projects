# UBER PICKUPS

## Project goals
**Create algorithms that will determine where are the hot-zones that drivers should be in.**
* Have a map with hot-zones using `plotly`
* Describe hot-zones per day of week. 
* Use two unsupervised algorithms like KMeans and DBScan. 

✅ Getting started with source data
There's a lot of files in the source folder.
* taxi-zone-lookup.csv : contains the LocationID, Borough, Zone name
* uber-raw-data-avr14.csv to uber-raw-data-sep14.csv contains the pickup date and time, latitude, longitude and base number (6 months --> 6 csv files)
* uber-raw-data-jan-jun-15.csv : contains the dispatching base number, pickup date and time, affiliated base number, location identifier (6 months --> 1 csv file)

✅ Data merging
We need to merge all of csv files to create a single dataframe.

✅ Data cleaning
* Drop columns that are not useful for our analysis
* Drop rows with missing values
* Drop rows with invalid values

✅ Data analysis
* Create a map with hot-zones using `plotly`
* Describe hot-zones per day of week.

✅ Modeling
We need to determine where are the hot-zones that drivers should be in.
* Use KMeans algorithm to cluster the data
* Use DBScan algorithm to cluster the data

✅ Conclusion