This contains code associated with the manuscript **'Discrete Global Grid Systems as scalable geospatial frameworks for characterizing coastal environments.'**

Four jupyter notebooks are used to walk through this code and demonstrate how environmental data can be processed and scaled using 2 DGGS implementations, [H3](https://github.com/uber/h3-py) and [dggridR](https://github.com/r-barnes/dggridR). Each notebook has specific python or R library requirements.

1. **Tampa_getWQP.ipynb**
    * This notebook explores retrieval of temperature point data from the Water Quality Portal (WQP) for the area of interest (Tampa Bay, FL) and pre-processing that data to remove unwanted points. The notebook includes code to save results either as a geoJSON or shapefile with point geometries for each temperature result. The data in the Water Quality Portal is constantly updated, meaning current query results will differ from the results at the time of this study. The data retrieved at the time of this study is included in the temperate_data folder to be used with H3/dggridR in subsequent notebooks. This data was split into two separate files, a geojson file with the sample points and a csv with the temperature results to limit the file size. This notebook was written to limit dependencies, we highly recommend using the [python dataretrieval](https://github.com/USGS-python/dataretrieval) or [R dataRetrieval](https://github.com/USGS-R/dataRetrieval) packages to query WQP data.

2. **Tampa_H3_Temperatures.ipynb**
    * This notebook uses python to explore aggregation of temperature data from WQP to H3 hexagons of different scales in the area of interest (Tampa Bay, FL). The notebook starts by walking through how to fill that area of interest polygon with H3 hexagons of different sizes. It then walks through aggregating water quality data to a given scale of hexagons, and how different time series aggregations result in different data density. Last it demonstrates use of k ring functionality to interpolate data across hexagons where sample data is lacking. This is the focal notebook and the requirements.txt file lists the dependencies required to run it.

3. **Tampa_dggridR_Temperatures.ipynb**
    * This notebook uses R to explore aggregation of temperature data from WQP to dggridR hexagons of different scales in the area of interest (Tampa Bay, FL). The notebook requires several R libraries to properly function. We recommend using anaconda to set up the R environment to run this notebook. dggridR must be installed from the tar.gz.

4. **Tampa_H3_Grid_SST.ipynb**
    * This notebook explores retrieval of [MUR Sea Surface Temperature (SST)](https://registry.opendata.aws/mur/) grid data for the area of interest (Tampa Bay, FL) and the two methods used to aggregate that data to either H3 scale 7 or scale 8 hexagons.

## EPA Disclaimer
The United States Environmental Protection Agency (EPA) GitHub project code is provided on an "as is" basis and the user assumes responsibility for its use. EPA has relinquished control of the information and no longer has responsibility to protect the integrity , confidentiality, or availability of the information. Any reference to specific commercial products, processes, or services by service mark, trademark, manufacturer, or otherwise, does not constitute or imply their endorsement, recommendation or favoring by EPA. The EPA seal and logo shall not be used in any manner to imply endorsement of any commercial product or activity by EPA or the United States Government.
