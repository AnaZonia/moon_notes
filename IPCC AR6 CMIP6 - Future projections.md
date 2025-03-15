---
up:
  - "[[002 Data Sources]]"
type:
  - climate
mission:
  - CMIP6
resolution: "-"
time_range: 2015-2100
url: https://www.wdc-climate.de/ui/q?hierarchy_steps_ss=IPCC-AR6_Reg_SAm&entry_type_s=Dataset
dg-publish: true
---
In the WDC climate link, as well as on [Google Earth Engine](https://developers.google.com/earth-engine/datasets/catalog/NASA_GDDP-CMIP6#description), we have data for many isolated models. However, just averaging these models is not a good representation of the real trajectory. There is an "ensemble" model that is a prediction taking into consideration all models.

I obtained the same data from [Copernicus](https://cds.climate.copernicus.eu/datasets/projections-cmip6?tab=download) using a script that summarizes the data across the different models.