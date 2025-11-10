# Houston Texas Extreme Weather Impacts

Identifying the impacts of extreme weather. This assignment will reinforce key concepts in geospatial analysis by practicing the following:  load vector/raster data simple raster operations simple vector operations spatial joins

## Learning outcomes
This assignment will reinforce key concepts in geospatial analysis by practicing the following:
-   **load vector/raster data**
-   **simple raster operations**
-   **simple vector operations**
-   **spatial joins**

## Background

Climate change is increasing the frequency and intensity of extreme weather events, with devastating impacts. “In February 2021, the state of Texas suffered a major power crisis, which came about as a result of three severe winter storms sweeping across the United States on February 10–11, 13–17, and 15–20.”1 For more background, check out these engineering and political perspectives.

In this assignment, you will identify the impacts of these series of extreme winter storms by estimating the number of homes in the Houston metropolitan area that lost power and investigate whether not these impacts were disproportionately felt.

Your analysis will be based on remotely-sensed night lights data, acquired from the Visible Infrared Imaging Radiometer Suite (VIIRS) onboard the Suomi satellite. In particular, you will use the VNP46A1 to detect differences in night lights before and after the storm to identify areas that lost electric power.

To determine the number of homes that lost power, you link (spatially join) these areas with OpenStreetMap data on buildings and roads.

To investigate potential socioeconomic factors that influenced recovery, you will link your analysis with data from the US Census Bureau.

When uploading data into RStudio, before pushing changes into Github, make sure to update the `.gitignore` to include `data` folder. 

The Data Structure Setup:
├── data
│   ├── ACS_2019_5YR_TRACT_48_TEXAS.gdb
│   │   ├── census tract gdb files
│   ├── gis_osm_buildings_a_free_1.gpkg
│   ├── gis_osm_roads_free_1.gpkg
│   └── VNP46A1
│       ├── VNP46A1.A2021038.h08v05.001.2021039064328.tif
│       ├── VNP46A1.A2021038.h08v06.001.2021039064329.tif
│       ├── VNP46A1.A2021047.h08v05.001.2021048091106.tif
│       └── VNP46A1.A2021047.h08v06.001.2021048091105.tif
├── Identifying_impacts_extreme_weather_files
├── Identifying_impacts_extreme_weather.html
├── Identifying_impacts_extreme_weather.qmd
├── Identifying_impacts_extreme_weather.Rproj
└── README.md

### Workflow outline:
To complete complete the tasks of this assignment, you will need to break your analysis into the following key steps:

- find locations that experienced a blackout by creating a mask *HINT: this will require creating a raster object for each day (2021-02-07 and 2021-02-16)*
: Check CRS of VNP raster files, combine, find difference, into night light intensity caused by storm between dates of interest. 
:
- exclude highways from analysis
: 
- identify homes that experienced blackouts by combining the locations of homes and blackouts
- identify the census tracts likely impacted by blackout
- Below is guidance and suggestions for each of these steps.

