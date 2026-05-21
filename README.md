# Exploratory Spatial Data Analysis: Spatial Autocorrelation and Choropleth Maps 
## Exploring Airbnb average listing prices in Canadian cities in 2022.

As a data analyst, you are familiar with Exploratory Data Analysis (EDA). It helps find out the patterns and relationships between variables and how they affect each other. In order to measure the relationship, you calculate the correlation coefficients and visualize them in a heat map.

What if you want to find the correlation between a variable and a location to get the patterns geographically?   
You cannot use EDA because it treats location data like other regular features. You need a new kind of analysis: Exploratory Spatial Data Analysis (ESDA). In lieu of the correlation and the heat map, the new measure is spatial autocorrelation, and the visualization is a choropleth map.

Instead of continuing with the theory, we should jump into an example now: Airbnb average listing prices in Canadian cities in 2022.   
Here is the process:

1. Import required libraries
2. Load listings data and neighbourhoods geodata of the chosen city
3. Convert the listings data to listings geodata
4. Join listings geodata and neighbourhoods geodata
5. Calculate the average price of every neighbourhood
6. Create an interactive choropleth map of the average listing price in the chosen city.   
   (I will also show the difference between the three classifications of the choropleth map.)
8. Determine the global spatial autocorrelation with Moran's I statistics to prove the presence (or absence) of clusters.
9. Determine the local spatial autocorrelation with LISA statistics and make a choropleth map of LISA cluster to show where the clusters are in the chosen city.   
   (I will verify the choropleth maps of some cities with their Moran's I values and p-values from the Moran's I statistics.)





---

**Data source**: *Inside Airbnb*  
http://insideairbnb.com/get-the-data/

Montreal

http://data.insideairbnb.com/canada/qc/montreal/2022-03-12/visualisations/listings.csv

http://data.insideairbnb.com/canada/qc/montreal/2022-03-12/visualisations/neighbourhoods.geojson

Quebec City

http://data.insideairbnb.com/canada/qc/quebec-city/2022-03-09/visualisations/listings.csv

http://data.insideairbnb.com/canada/qc/quebec-city/2022-03-09/visualisations/neighbourhoods.geojson

Toronto

http://data.insideairbnb.com/canada/on/toronto/2022-03-08/visualisations/listings.csv

http://data.insideairbnb.com/canada/on/toronto/2022-03-08/visualisations/neighbourhoods.geojson

Vancouver

http://data.insideairbnb.com/canada/bc/vancouver/2022-03-10/visualisations/listings.csv

http://data.insideairbnb.com/canada/bc/vancouver/2022-03-10/visualisations/neighbourhoods.geojson

Victoria

http://data.insideairbnb.com/canada/bc/victoria/2022-03-29/visualisations/listings.csv

http://data.insideairbnb.com/canada/bc/victoria/2022-03-29/visualisations/neighbourhoods.geojson

Winnipeg

http://data.insideairbnb.com/canada/mb/winnipeg/2022-06-08/visualisations/listings.csv

http://data.insideairbnb.com/canada/mb/winnipeg/2022-06-08/visualisations/neighbourhoods.geojson
