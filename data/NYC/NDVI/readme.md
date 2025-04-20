

---

# NYC NDVI Data Description

This dataset contains Normalized Difference Vegetation Index (NDVI) values extracted from satellite imagery for New York City (NYC), USA. The data covers several weeks between September 2021 and December 2021, with each file corresponding to a single week. The data is designed to facilitate spatial analysis of vegetation health over time.

## Data Structure

Each file corresponds to one week and includes the following columns:

- **OBJECTID**: A unique identifier for each record.
- **pointid**: Identifier for the point feature derived from the raster-to-point conversion process.
- **grid_code**: Represents the NDVI value at the specific location.
- **x**: Longitude coordinate of the point.
- **y**: Latitude coordinate of the point.
- **Date**: The date associated with the NDVI observation.

The naming convention for each file follows the pattern `LCYYYYMMDD`, where:
- `LC` refers to Landsat or Sentinel-2 data.
- `YYYY` represents the year.
- `MM` represents the month.
- `DD` represents the day.

For example, the file `LC20210911` corresponds to data collected on September 11, 2021.

## Data Processing Workflow

The NDVI values were calculated using multispectral satellite imagery from Sentinel-2 L2A and Landsat 8, following these steps:

1. **Data Collection**:
   - Satellite images were sourced from the [Copernicus Open Access Hub](https://scihub.copernicus.eu/) (Sentinel-2 L2A) and the [USGS EarthExplorer](https://earthexplorer.usgs.gov/) (Landsat 8).
   - Images were selected based on minimal cloud coverage and appropriate temporal resolution to ensure high-quality NDVI calculations.
   - The study area spans all five boroughs of NYC: Manhattan, Brooklyn, Queens, the Bronx, and Staten Island.

2. **NDVI Calculation**:
   - NDVI was computed using ArcGIS Pro's Raster Calculator tool. The formulas used were:
     - For **Landsat 8**: `(Band 5 - Band 4) / (Band 5 + Band 4)`
     - For **Sentinel-2**: `(Band 8 - Band 4) / (Band 8 + Band 4)`
   - These calculations provide a quantitative measure of vegetation health, where higher values indicate denser or healthier vegetation.

3. **Raster-to-Vector Conversion**:
   - The resulting NDVI rasters were clipped to the spatial boundaries of NYC.
   - Using ArcGIS Pro's Raster to Point tool, the raster data was vectorized into point features, with each point representing the centroid of a pixel and its corresponding NDVI value.
   - Geographic coordinates (latitude and longitude) were calculated for each point.

4. **Data Export**:
   - The final point datasets were exported to Excel and converted to `.csv` format for ease of use in further analyses.

## Interpretation of NDVI Values

- **Negative Values**: Represent clouds, water, and snow.
- **Values Close to Zero (≤ 0.1)**: Indicate bare soil or rocky areas.
- **Moderate Values (0.2–0.3)**: Correspond to shrubs and grasslands.
- **High Values (0.6–0.8)**: Represent dense vegetation such as forests or well-maintained urban green spaces.

## Intended Use

This dataset can be used to:
- Analyze weekly trends in vegetation health across NYC.
- Investigate spatial correlations between vegetation (NDVI) and air quality indicators, such as PM2.5 concentrations.
- Support urban planning and environmental management efforts by identifying areas with significant changes in vegetation cover.

## Notes

- Each file corresponds to a single week of data, allowing for weekly comparisons.
- The data is suitable for integration with other geospatial datasets using techniques like geohashing, enabling efficient spatial joins and large-scale analyses.
- This dataset complements publicly available air quality data for NYC, such as PM2.5 measurements collected via mobile sensors mounted on taxi vehicles. Combining NDVI and air quality data provides insights into the interaction between urban air quality and vegetation health.



---

