# Request-Logs
Analyse the request log of a service/product offered by a company and generate meaning results


The Task

Cleanup: A sample dataset of request logs is given in data/DataSample.csv. We consider records that have identical geoinfo and timest as suspicious. Please clean up the sample dataset by filtering out those suspicious request records.
Label: assign each request (from data/DataSample.csv) to one of the POI locations (from data/POIList.csv) that has minimum distance to the request location.

Analysis:
With respect to each POI location, calculate the average and standard deviation of distance between the POI location to each of its assigned requests.
Draw circles that are centered at each of the POIs, each includes all requests assigned to the POI location. Find out the radius and density (i.e. request count/circle area) for each POI location.

Model:
To visualize the popularity of the POI locations, we need to map the density of POIs into a scale from -10 to 10. Please give a mathematical model to implement the mapping. (Hint: please take consideration about extreme case/outliers, and aim to be more sensitive around mean average to give maximum visual differentiability.)
Try to come up with some reasonable hypotheses regarding POIs, state all assumptions, testing steps and conclusions. Include this as a text file (with a name bonus) in your final submission.


The Solution

Part I: Analyse and Visualize current Data
Step1: Import all needed libraries including pandas, numpy, matplotlib, seaborn sns, datetime, mathematical operator etc.
Step2: Read the request log file from the path using csv file readerand store it into a dataframe
Step3: Collect the info from a dataframe
Step5: Find the count of request logs per province
Step6: Find the top number of request logs per city
Problems found with data: Column header 'TimeSt' has an additional space at the begining, two POI locations has same latitude and longitude making the minimum distance calculation and allocation redundant for one.

Part II: Clean and Analyse the data again
Step7: Remove the fake request logs by the hypothesis that no two requests will happen within same minute and using duplicate drop principle to avaoid them.
Step8: Find the count of request logs per province after removing fake request
Step9: Find the number of top 5 request logs per city after fake request drop

Part III: POI List and allocation
Step10: Generate POI list as a dataframe with longitude and latitude values.
Step11: Calculate the distance between all request locations and various POI locations and find shortest distance and allocate the minimum distance POI to the request log.
Step12: Plot of mean distance of each POI to their respetive request logs.
Step13: Plot of variane between wach Poi and request log.

Part IV: Claculate density of each POI and come up with a mathematical model
Step 14: Density of number of request under each POI and mathematical model
