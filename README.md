# Surf_Shop_Analysis
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

We were able to run our temperature analysis from a statistically significant amount of temperature observations from which we can base our conclusions. While we've observed a notable difference in temperature results between the months of June and December, there exists a remarkable similarity between their own respective mean and median temperature measurements, suggesting few outlier days - and indeed, none to my eye are seen in the summary statistics we created. At the end of the day, W. Avy and I will need to carefully consider whether a surf and ice cream shop can survive over the winter months when temperatures *will* dip into the 50s, despite a low 70s average.

Further analysis into precipitation specific to these months would also be enlightening - is either June or December a very wet month? If, say, December is, perhaps December could simply be earmarked each year for closing for inventory, shop repairs, maintenance, and business plan review. Changing our code base to run this analysis would be simple, as we would only need to change from observing temperatures to observing precipitation. December, for example, would look like the following:

dec_results = session.query(Measurement.prcp, Measurement.date).\\
filter(func.strftime("%m", Measurement.date) == "12").all()

Another avenue of exploration would be more recent years of data. With the rapidly changing climate, observing weather data from 2010-2016 might not be the best timeframe from which to draw conclusions. Filtering our June data, for example, to look at the most recent year in our data set (2016) would look like the following: 

june_results = session.query(Measurement.tobs, Measurement.date).\\
filter(func.strftime("%m", Measurement.date) == "06").\\
filter(func.strftime("%Y", Measurement.date) == "2016").all()

and I also suspect W. Avy and I could obtain more recent data for a better analysis. 
