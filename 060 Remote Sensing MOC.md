Explore the options that there are and the methods for land use classification with remote sensing. Contact Javier, Hossein, Jeff Cardille and Elizabeth afterwards with possibilities.

https://samgeo.gishub.org/
https://joss.theoj.org/papers/10.21105/joss.05663

[[000 Data and Methods MOC]]

[(2) Avaliação de produtos para quantificar a área queimada MAP-FIRE - YouTube](https://www.youtube.com/watch?v=mcl2zSUTnAg)

spectral tools can tell the atmosphere
hyperspectral
radar


[[Labriere 2022- Toward a forest biomass reference measurement system for remote sensing applications]]
- New fund for STRI will help their own data collection of forest biomass data in and out of Panama: [Carbon verification | Smithsonian Tropical Research Institute (si.edu)](https://stri.si.edu/story/carbon-verification)

[[ECOSTRESS]]

![[Pasted image 20230818220314.png]]



ECOSTRESS
[Welcome to ECOSTRESS — ECOSTRESS (nasa.gov)](https://ecostress.jpl.nasa.gov/)


# verbesselt 2016
Temporal autocorrelation -> observations taken closely in time are correlated – slower change increases it. They looked at temporal autocorrelation in satellite data from tropical forests to see if there is evidence of slowing down of growth – but seeing change in slowness over time would need longer time series information, which is lacking. They looked at spatial patterns of slowness. NDVI (normalized difference vegetation index) shows plant activity, biomass and cover to tell forest health. Note – cloud cover may be an issue and needs to be accounted for. VOD – Vegetation optical depth, shows water content in biomass from RADAR data. They used regression to look at temporal autocorrelation at different moisture indexes. It is possible to infer slowness in forest growth from space, and temporal autocorrelation is probably a good indicator of resilience.
## asner 2013
Field inventory plots are expensive, difficult to maintain, and don't show heterogeneity. 

Mapped ACD - Aboveground Carbon Density using field plots, airborne LiDAR and Landsat at hectare scale. 

💡 The hectare is the most common unit, and is reliable for estimating errors in carbon stocks. 

Top of canopy height was measured at 1.1 m resolution, and it estimated ACD with high predictive power in relation to data collected from the ground (units Mg C /ha). 

Error of 10% in relation to field plots is within margin of error of field plots alone. 

ACD = 0.359 TCH^{1.7676} 

(field estimated ACD vs lidar estimated TCH) 

R squared was even higher among validation plots than on calibration plots (there's also fewer validation plots). 

Validation plots were used for national upscaling using satellite data. With decision tree, the nationwide upscaling was better (lower bias comparing nationwide to lidar scale data). 

The allometry to estimate biomass used wood density and taxonomy. 

What is the resolution? 

Can this be applied with GEDI data? 

May need to consider diversity in my study.
## decuyper 2022
Remote sensing of environment 

AVOCADO ALGORITHM 

What does it add to previous algorithms? 

- captures gradual change (unlike rgrowth, for example) 

- would be possible to incorporate logging for example 

- is less effective on dry tropical forest because NDMI of crops is quite similar to NDMI of the forest itself... so be careful with that. Regrowth was flagged accidentally. 

Some sociological factor studies only show the probability of permanence of forests depending on different sociological factors; forests may be allowed to regrow for 5-20 years before being cleared up again. This could just be a predictor for fallow period, but that’s gathered from remote sensing anyways, so it’s kind of useless for my study. 

The algorithm is calibrated with nearby mature forests.
## labriere 2022
Missions made to address this issue

NASA's GEDI

NASA-ISRO's NISAR

Limitations: Biomass goes up to 100Mg/há

ESA's BIOMASS
![[Screen Shot 2022-11-24 at 6.10.01 PM.png]]
- We need global standardized forest biomass reference measurements:

- At least 1ha sample plots
- Airborne LiDAR coverage
- Complementary terrestrial LiDAR

- Data is to be collected synchronously with Earth Observation
- Broad range of environmental conditions
- Sites are to be selected in areas where they are likely to be maintained in a long run by experts.

This study looks at 200 sites worldwide and sees how much they represent three dimensions of biomass:

Environmental

Temperature and prec (and their seasonality)

Solar radiation

TerraClimate dataset - na alternative to WorldClim?

Edaphic data (SoilGrids 2.0)

Physical (coarse fragment content and sand fraction)

Chemical (pH and CAC)

Geographical

How distant from each other are the plots?

Structural

Canopy height and tree cover fraction are both estimated from space.
Ducanson et al 2019 - These tools need to be validated with ground-truthed data.

Ducanson et al. 2021 - good practices for validation of biomass information

ForestPlots.net et al 2021 - RAINFOR

Davies et al. 2021 - ForestGEO

Anderson-Teixeira et al. (2015) or Hoffman et al. (2013) - Ran analyses on many variables that do covary/are correlated, but are unlikely to distort analysis - WHY?
## patterson 2019

The population parameter of interest is the average of the true AGBD over the N population elements (potential GEDI footprints), where N is the total number of population elements in a grid cell 

There is a parametric model, g(x, α), of AGBD in Mg ha−1 , where x are characteristics of the GEDI waveform for the GEDI footprint, and α is a vector of parameters. 

Performance of other lidar instruments suggests that canopy height and structure metrics derived from GEDI data will be strongly correlated with AGBD. 

In this paper, we propose the use of hybrid inference (Fattorini 2012, Ståhlet al 2016) to estimate mean AGBD, with associated uncertainty, at the level of the GEDI grid cell while explicitly accounting for both field-to-lidar model error as well as sampling uncertainty. 

a sample based estimate of mean AGBD within each grid cell. 

Random sample of clustered observations. 

Variance is estimated as a function of: (1) the number of clustered predicted footprint-level AGBD values and the variability among them, as well as (2) the uncertainty of the parameter estimates used in the footprint-level models. 

Deciduous needleleaf 

Deciduous broadleaf 

Evergreen needleleaf

Evergreen broadleaf (3441 plots) 

Grasses, shrubs and woodlands 
![[patterson2019.png]]

![[patterson20192.png]]

![[patterson20193.png]]