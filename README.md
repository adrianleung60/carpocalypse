# Carpocalypse!

<img src="https://github.com/adrianleung60/carpocalypse/blob/main/carpocalypse_logo.png" width="400" height="400">

### Project Team
Adrian Leung, Beatriz Lombeida Velasquez, Kathleen Gould, and Kristyll Avila 

Our team is exploring a Calgary without Cars. 
We asked ourselves questions like, “If cars and car infrastructure suddenly disappeared, what effect would that have on movement of people throughout the city?” and “How well connected is the non-car transport network?” and “What drives usage of the non-car transport network?”. We hope that our findings will provide useful information for city design and contribute to understanding efficient movement throughout the city without dependence on cars. 

## Collaboration Process and Methodology
1. Explored ideas using the Datathon Project Whiteboard methodology by GeoWomenYYC. Decided to focus on transit in the City of Calgary and how it relates to greenspace, walkability and bikeability.
2. Spatial data related to public trees, transit routes, bikeways, walkways, and communities were compiled into a QGIS project to stimulate ideas and accelerate divine inspiration.
3. After playing around with several datasets and consulting with the broader Datathon group, our topic was narrowed down in order to explore what the City of Calgary would look like in the hypothetical situation in which all personal transportation by cars was removed. 
4. Within a Google Colab notebook: 
    1. Spatial data was compiled with additional datasets (2014 household income, and 2017 population census data). Population and tree densities by community were calculated. 
    2. Accessed Walk Score APIs, Public Transit API, Bike Score APIs and ran K-means clustering using walk, bike and transit scores. Visualized cluster labels by community in notebook and QGIS.
    3. Merged datasets and performed multivariate analysis. Visualize as scatter matrix. 
    4. Output Pearson’s Correlation matrix to understand the strength of the relationship between the variables
Within QGIS, visualized clustering values by community together with stops and lines for major transit (LRT, BRT, MAX). Created a 500 m buffer around major transit lines to visualize the spatial extent of a moderate 10 minute walk to major transit and communities and other infrastructure that intersect these areas. 


## Pearson's Correlation Results 
- There is a positive correlation between tree density and walk/bike/transit scores. Investment in non-car mobility also tends to be investment in tree coverage.

- There is a negative correlation between median household income and scores. Could infer that higher household incomes are on the edges of the city that are not very walk/bikeable and have little transit and require a car to get around.

- There is a negative correlation between community size and scores. Larger communities could be more sprawled out, having less access to walkable hubs.

## Comments on Next Steps
- Street intersection density analysis including walkways and bikeways might provide more insight into the city’s car-less connectivity network.
- Incorporate bikeways and walkways usage data into maps (i.e., Strava heatmap, bike and pedestrian counts).
- Consider seasonal effects of bikeways and walkways usage. 
- Incorporate into the analysis routes needed for other stakeholders (i.e., mobility devices users).
- Incorporate extra data (population/tree density, income) into clustering method 

## Project Files
- QGIS Package - visualizing transit network and machine learning results
- Colab Notebook - code for backend data analysis and machine learning
- Maps Folder - primary maps created for visualizing final results
- walkbiketransitscores.csv - neighbourhood walk,bike and transit scores obtained from walkscore.com API

## References
### Datasets
The majority of the data used in this project is sourced from Open Calgary: Calgary's Open Data portal (https://data.calgary.ca) with additional data from other sources. 
The following data was sourced from Open Calgary. This information licensed under the Open Government Licence – City of Calgary: 
- Communities: https://data.calgary.ca/resource/j9ps-fyst.json 
- Major Road Network: https://data.calgary.ca/Transportation-Transit/Major-Road-Network/mybc-x96b 
- Bikeways: https://data.calgary.ca/Transportation-Transit/Calgary-Bikeways/yigb-2xmq 
- Transit Routes and Stops: https://data.calgary.ca/Transportation-Transit/Calgary-Transit-Routes-and-Stops/uxp9-udh5 
- Tree Cover: Public Trees Type and location: https://data.calgary.ca/Environment/Urban-Forest-Public-Tree-Locations/uwi9-9nzk 
- Population census data (2017): https://data.calgary.ca/resource/jtpc-xgsh.json?census_year=2017-04-01T00:00:00.000

### Additional data sources:
- Walk Score APIs - Public Transit API, Bike Score API: www.walkscore.com
- Household Income (2014): https://great-news.ca/demographics 
- Basemap: Maxar Technologies, CNES/Airbus, Google. Obtained through Google Satellite Imagery using HCMGIS plugin.

### Tools and Software
- Colaboratory (Colab) Jupyter notebook environment
- QGIS: free and open-source cross-platform desktop geographic information system application

