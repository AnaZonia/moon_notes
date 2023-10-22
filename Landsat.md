---
up:
  - "[[Remote Sensing]]"
type:
  - "[[Multispectral]]"
source:
  - NASA
resolution: 30m
time range: 1985-
url: https://www.usgs.gov/landsat-missions
---
[Landsat 8 Collection 1 (C1) Land Surface Reflectance Code (LaSRC) Product Guide (amazonaws.com)](https://d9-wret.s3.us-west-2.amazonaws.com/assets/palladium/production/s3fs-public/atoms/files/LSDS-1368_L8_C1-LandSurfaceReflectanceCode-LASRC_ProductGuide-v3.pdf)

Landsat files are rescaled up to 10,000 to turn data into integers, so it's easier to download and has less file size than floats.

## Overview
![[Landsat-2.png]]
- This image shows the bandpass wavelengths for the Landsat 1-9 sensors. Landsat MSS = the numbers shown are for Landsat 4 and Landsat 5; Landsat 1-3 band numbers are 4, 5, 6 and 7.
- MSS bands 1-4 were known as bands 4-7, respectively, on Landsats 1-3

![[Landsat-3.png]]
Can be useful for *land use classification* due to differences in leaf pigmentation, structure and moisture - mostly very small scale chemical and physical properties. Very different from [[SAR]]!

## History
Landsat 1-3 was an experimental program.
**Landsat 4-5 carried:**
- *the Multispectral Scanner (MSS)*
	- Four spectral bands (identical to Landsat 1 and 2):
	    - Band 4 Visible Green (0.5 to 0.6 µm) — powered off due to high current in August 1995
	    - Band 5 Visible Red (0.6 to 0.7 µm)
	    - Band 6 Near-Infrared (0.7 to 0.8 µm)
	    - Band 7 Near-Infrared (0.8 to 1.1 µm)
- Six detectors for each spectral band provided six scan lines on each active scan
- Ground Sampling Interval (pixel size): 57 x 79 m
- *the Thematic Mapper (TM)*
	- - Added the mid-range infrared to the data
	- Seven spectral bands, including a thermal band:
	    - Band 1 Visible Blue (0.45 - 0.52 µm) 30 m
	    - Band 2 Visible Green (0.52 - 0.60 µm) 30 m
	    - Band 3 Visible Red (0.63 - 0.69 µm) 30 m
	    - Band 4 Near-Infrared (0.76 - 0.90 µm) 30 m
	    - Band 5 Near-Infrared (1.55 - 1.75 µm) 30 m
	    - Band 6 Thermal (10.40 - 12.50 µm) 120 m
	    - Band 7 Mid-Infrared (2.08 - 2.35 µm) 30 m
	- Ground Sampling Interval (pixel size): 30 m reflective, 120 m thermal
 **Landsat 6** failed 
 **Landsat 7** carried the *Enhanced Thematic Mapper Plus (ETM+)*
 The new band 8, Panchromatic, gives 15m spatial resolution.

**Landsat 8** carries the *Operational Land Imager (OLI) and the Thermal Infrared Sensor (TIRS).*

![[Landsat-1.png]]
**Landsat 9 OLI-2** works exactly the same as Landsat 8 OLI.
**Landsat 9 TIRS-2** improves on Landsat 8 OLI.
	Same two bands:
	- Band 10 TIRS 1 (10.6 - 11.19 µm) 100-m
	- Band 11 TIRS 2 (11.5 - 12.51 µm) 100-m
But they minimize stray light.

**Landsat 8 and 9 work as a constellation**, so they have an 8-day return window.

Landsat Next will have three satellites.

## Collections, Tiers and Levels
**Collection 1** was an organization of the whole data so that it is in a constant archive - now unavailable as it's obsolete.
**Collection 2** is the second major reprocessing, with many product improvements.
- **Tier 1 (T1)** - Data that meets geometric and radiometric quality requirements
- **Tier 2 (T2)** - Data that doesn't meet the Tier 1 requirements
- **Real Time (RT)** - Data that hasn't yet been evaluated (it takes as much as a month).

## Science Products
- **Provisional Actual Evapotranspiration (L3)** 
	- The quantity of water that is removed from a surface due to the processes of evaporation and transpiration
- **Surface Temperature (L2)**
- **Provisional Aquatic Reflectance (L2 - only Landsat 8-9)**
	- Spectral distribution of visible solar-reflected radiation upwelling from the upper water column
- **Surface Reflectance (L2)**
![[Landsat-4.png]]
This [product](https://www.usgs.gov/landsat-missions/landsat-collection-2-surface-temperature) is generated from multiple data sources and atmospheric profiles, including NASA's [ASTER](https://lpdaac.usgs.gov/products/ag100v003/)(Thermal Emission and Reflection Radiometer). Some areas are missing ASTER data since there was too much persistent cloud cover, so that data is missing in Landsat SR.
### Derived Spectral Indices (L2)
Derived from Surface Reflectance.
#### EVI - Enhanced Vegetation Index

#### NDVI - Normalized Difference Vegetation Index

#### SAVI - Soil Adjusted Vegetation Index

#### MSAVI - Modified Soil Adjusted Vegetation Index

#### NDMI - Normalized Difference Moisture Index
#### NBR - Normalized Burn Ratio (1 and 2)

![[Landsat.png|Infrared (band 7) shows fire scars much better than the standard images (Landsat 7)]]

Requires a sequence of images to be calculated (variation in NBR detects burn)


## Cleaning Clouds

![[Landsat-5.png]]

Cloud shadow masking may not be available for all years of landsat - make sure to check how quality assurance works for older landsat.
