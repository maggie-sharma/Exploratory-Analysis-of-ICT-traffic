# Exploratory Analysis of ICT Traffic Accidents
Exploratory data analysis using Excel, SQL, and Tableau

## Author: Maggie Sharma
#### Date: 11/23/2021


# Purpose
Explore publicly available traffic accident data for Wichita, KS using Excel, SQL, and Tableau

## Guiding Questions

* What day of the week has the most traffic accidents?
* Where do the most traffic accidents occur?
* How many accidents occur along the main highways?
* What time of day do the most traffic accidents occur?

## Preparing the Data


The data was collected from the City of Wichita’s Open Data Portal via access.wichita.gov. The dataset includes traffic accident reports from February 1, 2020 through April 4, 2021. [source](https://ict-opendata-cityofwichita.hub.arcgis.com/datasets/1a082b52f46148bcb73f09cdd142c894_0/about)

The dataset was exported for initial cleaning to an Excel spreadsheet. No duplicate values were found. As the primary objective of this analysis focuses on location of accident, 29 entries that did not contain the Beat number were removed. Entries without an address were included as long as the Beat number was included. Since all entries occurred in the Wichita metro, missing City entries were filled in with “Wichita.”  To look at the time of day distribution of accidents, the time was separated from the date and formatted as time. Columns without data were removed. 

# Incidents by police beat and day of the week

Using Excel, a PivotTable showing the total number of accidents by day of the week and police beat was created. Then the total incidents per day of the week were graphed using Tableau. 

![](https://github.com/maggie-sharma/Exploratory-Analysis-of-ICT-traffic/blob/main/pivot%20table2.png?raw=true)



![](https://github.com/maggie-sharma/Exploratory-Analysis-of-ICT-traffic/blob/main/tableau%20chart.png?raw=true)

Through the PivotTable and chart, we see that Friday has the most accidents followed by Thursday. Sunday and Saturday had the least amount of accidents. 


Using the values generated with the pivot table on Excel, the percentage of incidents per day were calculated. Conditional formatting was applied to easily identify police beats with higher than average incidents and lower than average incidents. 

![](https://github.com/maggie-sharma/Exploratory-Analysis-of-ICT-traffic/blob/main/conditional%20formatting.png?raw=true)

### Summary of day of the week analysis 

* Most police beats had a higher percentage of incidents on Friday, but several police beats had a higher percentage of incidents occur on Thursday. 

* While most police beats saw the end of the work week to have the higher percentages of incidents, police beats 17 and 21 saw the most incidents occur on Mondays.  

* Interestingly, police beat 34 saw a different breakdown than other police beats with a smaller percentage of accidents on Tuesday/Thursday and higher percentages Sunday/Monday.

# Location of Traffic Accidents

Importing the Wichita Police Department Beat Finder onto Tableau was not available with Tableau Public. Instead the publicly available Wichita Police Department Beat Finder map was used. 
![](https://github.com/maggie-sharma/Exploratory-Analysis-of-ICT-traffic/blob/main/police%20beat%20map.png?raw=true)
[source](https://www.arcgis.com/apps/webappviewer/index.html?id=f3e02b14547c49c9a63a04e33fba04a4)

Earlier, it was found that beats 19, 31, 37, and 39 appear to have the highest number of accidents. Police beat 31 covers the downtown district of Wichita, but beats 19, 37, and 39 are not downtown. In fact, beat 19 covers a primarily residential suburban area. 


Since beat 19 is in a more suburban area, it was hypothesized that perhaps beat 19 sees different types of incidents such as animal involved accidents. To look at the breakdown of types of incidents for the four police beats with the highest number of incidents, see the below graph:

![](https://github.com/maggie-sharma/Exploratory-Analysis-of-ICT-traffic/blob/main/top%204.png?raw=true)


As we can see beat 19 had a similar breakdown of incident types compared to beats 31, 37, and 39. The majority of incidents were categorized as Motor Veh-In Transport. In fact, there were *no animal related incidents* in police beat 19 despite being a suburban location. 

### Location Analysis using SQL




![](https://github.com/maggie-sharma/Exploratory-Analysis-of-ICT-traffic/blob/main/SQL%20KELLOGG%20STATEMENT.png?raw=true)


Kellogg Avenue is the main East-West highway in Wichita. Using SQL, the total address that contained ‘Kellogg’ equaled 1,087 and the total incidents equaled 9384. **Accidents occurring on Kellogg accounted for 12% of incidents.**



![](https://github.com/maggie-sharma/Exploratory-Analysis-of-ICT-traffic/blob/main/135%20total.png?raw=true)


I-135 is the main north-south interstate that intersects Wichita. Using SQL, 159 incidents occurred along I-135, which accounts for **2% of incidents.**


# Time of Day of Accident Analysis

![](https://github.com/maggie-sharma/Exploratory-Analysis-of-ICT-traffic/blob/main/TIME%20OF%20DAY%20SQL.png?raw=true)

![](https://github.com/maggie-sharma/Exploratory-Analysis-of-ICT-traffic/blob/main/time%20of%20day%20chart.png?raw=true)

Using SQL and Excel, we can see that the majority of accidents occurred in the afternoon (Noon-5:00p.m.) timeframe. 

# Conclusions: 
* Most accidents occurred toward the end of the work week, with Friday seeing the most incidents.
* Most accidents occurred in the afternoon.
* 12% of accidents occurred along U.S. 54 Kellogg 
* Police beat 19, a northwestern suburb, had the highest amount of accidents. 

## Further points to consider

It would be interesting to investigate the high number of incidents in police beat 19 given further data. Perhaps there are more stop signs in this area or specific intersections with high incident rates. Investigating the cause of incidents may allow the police force to implement changes in the area to reduce accidents. 

The city of Wichita police department may want to allocate more police staffing for Thursday/Friday as incident rates increased on these days. Police may want to focus on reducing incidents in high areas, such as by running awareness campaigns in targeted zones or increasing presence during busy times. Further data analysis on time of day may help identify patterns further.

Further analysis of areas of lower than average traffic incidents may also shed light on how to reduce traffic incidents in other parts of town. 
