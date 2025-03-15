---
up:
  - "[[SAR]]"
  - "[[002 Data Sources]]"
  - "[[Remote Sensing]]"
type:
  - biomass
mission:
  - "[[GEDI]]"
  - "[[ASAR-ESA]]"
  - "[[PALSAR - ALOS]]"
  - "[[Sentinel 1]]"
resolution: 100m
time_range: 2010, 2017, 2018, 2019, 2020
url: https://catalogue.ceda.ac.uk/uuid/af60720c1e404a9e9d2c145d2b2ead4e
---
	Summary of [Key Documents](https://climate.esa.int/en/projects/biomass/key-documents/)
- [Santoro et al. 2021 - The global forest above-ground biomass pool for 2010 estimated from high-resolution satellite observations](https://essd.copernicus.org/articles/13/3927/2021/)
- [Santoro's presentation explaining the project](https://climate.esa.int/sites/default/files/D1_S1_T3_Santoro.pdf)
[The ESA BIOMASS mission MOOC](https://eo-college.org/resource/the-esa-biomass-mission/)



GlobBiomass -> CCI Biomass CORE -> [Biomass](https://www.esa.int/Applications/Observing_the_Earth/FutureEO/Biomass)
[Key Documents (esa.int)](https://climate.esa.int/fr/projects/biomass/key-documents/)
## Introduction to the method
[More method information](https://dopa.jrc.ec.europa.eu/var/www/app/app/static/dopa/files/factsheets/en/DOPA%20Factsheet%20J2%20EN%20Above-Ground%20Carbon.pdf)

Map was developed using EO as well as in-situ data.

Other datasets were available with AGB based on remote sensing, but most use data around 2000 or have coarse resolution.

==Cross comparisons show estimates are different at local scale.==
- this may show it's a good idea to do a cross-comparison of ESA GlobBiomass and GEDI.


![[santoro20181.png]]


Growing stock volume (m^3 ha-1) was estimated, and then AGB was gotten from that.

## Methods

Standard deviation was calculated with the standard deviation of the backscatter, and estimates of forest backscatter model parameters.

Uses [[ICESat1 - GLAS & ICESat2 - ATLAS]] and [[GEDI]] for calibration.

Error models have been defined to characterize uncertainties associated with the backscatter measurements, the estimation of the model parameters for each image in the multi-temporal stack of observations, and the error associated with supporting datasets, such as ICESAT GLAS.
- Could the SD of early biomass values can be larger because there's more variability in the residuals in early trajectories

*How did ESA Biomass incorporate GEDI - and what does that mean for systemic bias aka more issues with lower biomass values?*
- With the denser coverage of GEDI and ICESat-2, the allometries between AGB and tree height were further characterized in Year 3. The impact of the allometries on the AGB maps was substantial, reducing the overestimation in the low AGB range and underestimation in the high AGB range.
## Biomass 2024
Upcoming P-band SAR to be released in 2024
The amount of biomass and forest height will be measured at a resolution of 200 m, and forest disturbances such as clear-cutting at a resolution of 50 m

![[ESA CCI Biomass.png]]

