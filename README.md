# 🌊 Flood Impact Assessment 

## Overview

This project focuses on performing a detailed flood impact assessment using **Google Earth Engine (GEE)** and **Landsat 9 satellite imagery**. The analysis compares pre-flood and post-flood conditions to detect changes in surface water and vegetation cover through the use of spectral indices such as the **Normalized Difference Water Index (NDWI)** and the **Normalized Difference Vegetation Index (NDVI)**. By quantifying variations between two time periods, the script identifies flooded zones and areas of vegetation damage, calculates their extent in hectares and percentage, and exports both visual and statistical outputs for further analysis.

---

## Workflow Description

The workflow begins with loading the **Area of Interest (AOI)**, which can either be uploaded as a shapefile asset or drawn directly within the GEE code editor. Once the AOI is defined, the script automatically retrieves Landsat 9 Collection 2, Level-2 imagery corresponding to pre-flood and post-flood dates provided by the user. Images are filtered to include only those with less than 20% cloud cover, ensuring clear observations. If the AOI spans multiple satellite tiles, a mosaic of multiple scenes is generated to produce a seamless image composite.

---

## Index Computation and Analysis

For each time period, the script calculates NDWI and NDVI indices. The NDWI, derived from the green and near-infrared bands, enhances open water features and highlights inundated areas. The NDVI, derived from near-infrared and red bands, reflects vegetation greenness and health. By subtracting pre-flood NDWI from post-flood NDWI, and similarly for NDVI, the script generates change maps that reveal water spread and vegetation loss. An NDWI increase greater than 0.1 is interpreted as flood presence, while an NDVI decrease below -0.1 indicates vegetation damage. These thresholds can be adjusted according to study needs or field conditions.

---

## Area Calculation and Statistics

After classification, the script calculates the total AOI area and the affected regions using pixel-based area estimation. Each pixel’s area is determined in square meters and converted to hectares for easier interpretation. The results include the total area, flooded area, and vegetation damage area, along with their respective percentages relative to the AOI. The mean, minimum, and maximum NDWI and NDVI values are also computed for both pre-flood and post-flood images, offering valuable statistical insight into the intensity and extent of the flood event.

---

## Visualization and Map Outputs

The results are visualized through several map layers. True-color composites of pre-flood and post-flood scenes allow easy visual comparison. NDWI and NDVI maps are rendered using color palettes that distinguish between water, vegetation, and bare surfaces. Change detection layers clearly highlight flood-affected and vegetation-stressed zones, using red and blue hues for intuitive interpretation. All visual layers are displayed in GEE and can be individually toggled on or off for better visualization control.

---

## Export and Data Products

To support further use and sharing, the script exports all major outputs to Google Drive. These include GeoTIFF images of NDWI and NDVI for both pre-flood and post-flood conditions, their respective change maps, and true-color composites. The identified flooded areas and vegetation damage zones are also exported as GeoTIFF layers for integration into GIS software. Additionally, a summary shapefile is created containing essential numerical results such as total AOI area, flooded area, vegetation loss area, and their percentages. This summary enables straightforward inclusion in reports, maps, and spatial analyses.

---

## Applications

This project provides an efficient, automated method for assessing the impact of floods on both land and vegetation. It can be applied to disaster management, crop damage estimation, hydrological and environmental monitoring, and regional planning. Because it uses freely available satellite data and cloud computing through Google Earth Engine, it offers a scalable and cost-effective solution for quick and reliable flood impact assessments across different regions.
