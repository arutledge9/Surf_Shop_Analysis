# surfs_up
Module 9 coursework w/ python, sqlite, flask


## Summary

I have been working with my friend W. Avy to analyze the feasibility of opening up a surf and ice cream shop in Oahu, since we both love surfing and ice cream so much. However, we don't want to rush in without a full analysis of all data and weather points, because we'd hate to launch our dream venture only to see it fail due to weather behavior we could have easily researched and anticipated with a little foresight. We've been working with SQLite, SQLAlchemy, and Flask on all of our analyses, which until this point have looked at a year's worth of precipitation data across a number of Hawaiian Islands weather stations, as well as temperature data from the most active station. W. Avy has asked me to take a final look at the historical temperature data in June and also in December to make sure our shop can remain open year-round. 


## Results

A quick snapshot of summary statistics from June

![](/Resources/june_results.PNG)

and from December

![](/Resources/december_results.PNG)

show that: 
- while both sets only deviate from their mean temperatures by 3-4 degrees on average, the lowest recorded temperatures in December are 8 whole degrees lower than they are in June,
- the average and median temperatures in June (75) are more comfortable than their December counterparts (71),
- and that while the heat in days from both sets don't deviate much from their average temperatures, those in the month of December do so by slightly half a degree more than the days in June - meaning more temperature fluctuation in the winter when we want to be out on our boards. 

## Summary
- a statistically significant amount of temperature observations from which we can base our conclusions,
- a remarkable similarity between their own respective mean and median temperature measurements,
