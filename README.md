# Houston Texas Extreme Weather Impacts
Author: Marie Tolteca, Student at Bren School of Environmental Science and Management, Masters in Environmental Data Science
Date 11/10/2025

**This project examines the impacts of the February 2021 Texas winter storms that caused widespread power outages across the state. Using VIIRS night light data (VNP46A1), the analysis identifies areas in the Houston metropolitan region that experienced blackouts by comparing light intensity before and after the storm. These areas are then spatially joined with OpenStreetMap building data to estimate the number of affected homes and with U.S. Census data to explore potential socioeconomic disparities in the blackout’s impacts.**

```         
 #........................Learning Outcomes.......................
```
#### Key geospatial analysis concepts: 
- Raster analysis (detecting changes in satellite imagery) 
- Vector operations (buffering, intersections, spatial joins) 
- Loading and managing vector/raster data 
- Performing raster calculations (differences in nightlight intensity) 
- Conducting spatial joins and intersections 
- Linking spatial data with census information

```         
 #..........................Data Access...........................
```
- All project data (above) can be accessed via this Google Drive link.|
[Google Drive Download](https://drive.google.com/file/d/1bTk62xwOzBqWmmT791SbYbHxnCdjmBtw/view?usp=drive_link) |
**Nightlight Data (VNP46A1)**
- VIIRS Day/Night Band imagery (before and after the storm) used to detect blackout regions.
[NASA LAADS DAAC](https://ladsweb.modaps.eosdis.nasa.gov/) |
**Roads and Buildings**
- OpenStreetMap vector data for Texas; used to identify homes and major highways in Houston.
[Geofabrik Download Server](https://download.geofabrik.de/) |
**Socioeconomic Data**
- 2019 ACS 5-Year Estimates for Texas census tracts, including median household income.|
[U.S. Census Bureau](https://www.census.gov/programs-surveys/acs/news/data-releases.2023.html#list-tab-1133175109)

```         
 #......................Reprository Structure.....................
```
**When uploading data into RStudio, before pushing changes into Github,make sure to update the `.gitignore` to include `data` folder.**
**My Data Reprository Structure:**

<img width="463" height="471" alt="Screenshot 2025-11-10 at 8 00 58 PM" src="https://github.com/user-attachments/assets/41da3c5b-bdf5-453d-b956-f914ec2d7858" />

```         
 #........................Workflow Outline........................
```
#### Library Package Usage:
**In this project, the following packages will be used. If the library needs to be installed use `install.packages()` to install libraries. Terra, tidyyverse, tmap, kableExtra, spData, spDataLarge, geodata, here, sf, raster, and stars.**
#### Identify blackout regions:
-   **Combine VIIRS raster tiles for dates before and after the storm.**
-   **Compute the difference in nightlight intensity.**
-   **Reclassify areas with a drop greater than 200 nW/cm²/sr as blackout zones.** 
#### Locate affected homes
-   **Load Houston’s OSM building data.**
-   **Perform a spatial intersection with blackout polygons.**
-   **Estimate total homes impacted.**
#### Socioeconomic 
-   **Spatially join census tracts with blackout regions.**
-   **Compare median household incomes between affected and unaffected tracts using boxplots and summary statistics.**
```    
  #............................Outputs.............................
```
In the images folder, a before and after rasters for VNPs, reclassified map, blackout houston map, a highway buffer on the houston map,buildings impacted, and a barplot for the median income

    #........................Acknowledgements........................
This repository was produced as part of teaching material for EDS 223:Identifying the impacts of extreme weather, taught by Annie Abrams. Author of Homework Assignment 3, author Ruth Oliver.
- **NASA Earth Observations (VIIRS Nighttime Lights)** 
- **U.S. Census Bureau, American Community Survey (ACS 2019 5-Year Estimates)**  
- **OpenStreetMap and Geofabrik for base vector data** 
```
    #........................Reproducibility.........................
```
**All analysis was conducted in RStudio using the packages listed above. Code is contained in the `Identifying_impacts_extreme_weather.qmd` file, and outputs are saved in the images/ directory.**
