---
up:
  - "[[002 Data Sources]]"
type:
  - climate
  - cwd
  - aet
  - radiation
mission:
  - WorldClim, CRU and Japanese Reanalysis
resolution: 1/24 degree (~4km)
time_range: Monthly, 1958-2020
url: https://www.climatologylab.org/terraclimate.html
---
![](https://i.imgur.com/D0JD4eW.png)


[[Cumulative Water Deficit]] used in Heinrich et al 2021. Needs MCWD R script to work (https://zenodo.org/record/2652658#.X9CV-aFxdPY).

[Abatzoglou et al 2018 - TerraClimate, a high-resolution global dataset of monthly climate and climatic water balance from 1958–2015](https://www-nature-com.proxy3.library.mcgill.ca/articles/sdata2017191#Tab1)
- AET is calculated with grasses as a reference, so not useful for us.
- precipitation is used from WorldClim, Climate Research Unit (CRU) and Japanese 55-year Reanalysis (JRA).