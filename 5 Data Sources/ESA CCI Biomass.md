---
up:
  - "[[SAR]]"
  - "[[003 Data Sources]]"
  - "[[110 Remote Sensing]]"
type:
  - biomass
mission:
  - "[[GEDI]]"
  - "[[ASAR-ESA]]"
  - "[[ALOS1-2-JAXA]]"
  - "[[Sentinel 1]]"
resolution: 100m
time_range: 2010, 2017, 2018, 2019, 2020
url: https://catalogue.ceda.ac.uk/uuid/af60720c1e404a9e9d2c145d2b2ead4e
---
[CEDA Archive Web Browser](https://data.ceda.ac.uk/neodc/esacci/biomass/data/agb/maps/v4.0/geotiff/2018)

GlobBiomass -> CCI Biomass CORE -> [Biomass](https://www.esa.int/Applications/Observing_the_Earth/FutureEO/Biomass)

[Santoro et al. 2021 - The global forest above-ground biomass pool for 2010 estimated from high-resolution satellite observations](https://essd.copernicus.org/articles/13/3927/2021/)

[Santoro's presentation explaining the project](https://climate.esa.int/sites/default/files/D1_S1_T3_Santoro.pdf)

### Introduction to the method

Map was developed using EO as well as in-situ data.

Other datasets were available with AGB based on remote sensing, but most use data around 2000 or have coarse resolution.

==Cross comparisons show estimates are different at local scale.==
- this may show it's a good idea to do a cross-comparison of ESA GlobBiomass and GEDI.


![[santoro20181.png]]


Growing stock volume (m^3 ha-1) was estimated, and then AGB was gotten from that.

## Methods

Standard deviation was calculated with the standard deviation of the backscatter, and estimates of forest backscatter model parameters.

Uses [[ICESat1 - GLAS & ICESat2 - ATLAS]] and [[GEDI]] for calibration.

Upcoming P-band SAR to be released in 2024

![[ESA CCI Biomass.png]]

