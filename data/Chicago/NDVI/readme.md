
---

# Chicago NDVI Data Description

This dataset contains Normalized Difference Vegetation Index (NDVI) values extracted from satellite imagery for the city of Chicago, USA, covering several months between 2021 and 2023. The data is structured to facilitate spatial analysis of vegetation health over time.

## Data Structure

Each file corresponds to one month and includes the following columns:

- **OBJECTID**: A unique identifier for each record.
- **pointid**: Identifier for the point feature derived from the raster-to-point conversion process.
- **grid_code**: Represents the NDVI value at the specific location.
- **x**: Longitude coordinate of the point.
- **y**: Latitude coordinate of the point.
- **Date**: The date associated with the NDVI observation.

## Data Processing Workflow

The NDVI values were calculated using multispectral satellite imagery from Sentinel-2 L2A and Landsat 8, following these steps:

1. **Data Collection**:
   - Satellite images were sourced from the [Copernicus Data Space Ecosystem](https://scihub.copernicus.eu/) (Sentinel-2 L2A) and the [USGS EarthExplorer](https://earthexplorer.usgs.gov/) (Landsat 8).
   - Images were selected based on minimal cloud coverage and appropriate temporal resolution to ensure high-quality NDVI calculations.

2. **NDVI Calculation**:
   - NDVI was computed using ArcGIS Pro's Raster Calculator tool. The formulas used were:
     - For **Landsat 8**: `(Band 5 - Band 4) / (Band 5 + Band 4)`
     - For **Sentinel-2**: `(Band 8 - Band 4) / (Band 8 + Band 4)`
   - These calculations provide a quantitative measure of vegetation health, where higher values indicate denser or healthier vegetation.

3. **Raster-to-Vector Conversion**:
   - The resulting NDVI rasters were clipped to the spatial boundaries of Chicago.
   - Using ArcGIS Pro's Raster to Point tool, the raster data was vectorized into point features, with each point representing the centroid of a pixel and its corresponding NDVI value.
   - Geographic coordinates (latitude and longitude) were calculated for each point.

4. **Data Export**:
   - The final point datasets were exported to Excel and converted to `.csv` format for ease of use in further analyses.

## Interpretation of NDVI Values

- **Negative Values**: Represent water bodies, snow, or clouds.
- **Values Close to Zero (≤ 0.1)**: Indicate bare soil or rocky areas.
- **Moderate Values (0.2–0.3)**: Correspond to shrubs and grasslands.
- **High Values (0.6–0.8)**: Represent dense vegetation such as forests or well-maintained urban green spaces.

## Intended Use

This dataset can be used to:
- Analyze temporal trends in vegetation health across Chicago.
- Investigate spatial correlations between vegetation (NDVI) and other environmental factors, such as air quality (e.g., PM2.5 concentrations).
- Support urban planning and environmental management efforts by identifying areas with significant changes in vegetation cover.

## Notes

- Each file corresponds to a single month of data, allowing for monthly comparisons.
- The data is suitable for integration with other geospatial datasets using techniques like geohashing, enabling efficient spatial joins and large-scale analyses.



---
