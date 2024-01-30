---
up:
  - "[[Remote Sensing]]"
type:
  - "[[LiDAR]]"
source:
  - NASA
resolution: 25m-1km
time range: 04/2019-08/2021
url: https://daac.ornl.gov/cgi-bin/dsviewer.pl?ds_id=2017
---
[Geo for Good 2021 : Novel Forest Data & Applications Part 1: GEDI & Obiwan - YouTube](https://www.youtube.com/watch?v=PQwVDnOsqhQ&list=WL&index=10)

GEDI has so much more data than other efforts (Saatchi, Baccini) that it should be able to produce more biomass products.

The GEDI L4A Footprint Biomass product converts each high-quality waveform to an AGBD prediction, and the L4B product uses the sample present within the borders of each 1 km cell to statistically infer mean AGBD.

![[GEDI.png|University of Maryland - NASA]]
### 4A
Deciduous tropical forests are underrepresented.

The algorithm setting group selection used for GEDI02_A Version 2 has been modified for Evergreen Broadleaf Trees in South America to reduce false positive errors resulting from the selection of waveform modes above ground elevation as the lowest mode.

GEDI04_A models were developed using a quality-filtered calibration dataset that contains simulated GEDI waveforms and field estimates of AGBD: the Forest Structure and Biomass Database (FSBD). 

Footprint AGBD was derived from parametric models that relate simulated GEDI Level 2A (L2A) waveform relative height (RH) metrics to field plot estimates of AGBD. Height metrics from simulated waveforms associated with field estimates of AGBD from multiple regions and plant functional types (PFTs) were compiled to generate a calibration dataset for models representing the combinations of world regions and PFTs (i.e., deciduous broadleaf trees, evergreen broadleaf trees, evergreen needleleaf trees, deciduous needleleaf trees, and the combination of grasslands, shrubs, and woodlands).
Methods algorithm for generating 4A
[Algorithm Theoretical Basis Document for GEDI Footprint Aboveground Biomass Density (mcgill.ca)](https://agupubs-onlinelibrary-wiley-com.proxy3.library.mcgill.ca/doi/epdf/10.1029/2022EA002516)


[gedi_tutorials/1_gedi_l4a_search_download.ipynb at main · ornldaac/gedi_tutorials (github.com)](https://github.com/ornldaac/gedi_tutorials/blob/main/1_gedi_l4a_search_download.ipynb)

[ornldaac/gedi_tutorials: GEDI L3 and L4 Tutorials (github.com)](https://github.com/ornldaac/gedi_tutorials)
[HDF® View - The HDF Group](https://www.hdfgroup.org/downloads/hdfview/)
[How to download and map GEDI Space-borne LiDAR data(focus to L2A) – Go with the flow (home.blog)](https://fivequestionz.home.blog/2020/01/27/how-to-download-and-map-gedi-space-borne-lidar-datafocus-to-l2a/)
According to Shrestha, the GEDI Level 4B dataset complements the [Level 4A Version 2](https://doi.org/10.3334/ORNLDAAC/2056) product released in December 2021 and provides a statistically derived gridded version of the footprint-level estimates from GEDI Level 4A data.
light bounces back
[PeterBoswell | GEDI forest transects](https://www.peterboswell.me/activities/open-source-mapping/gedi-forest-transects/#:~:text=h5%20file%20in%20a%20directory,)%20and%20elevation%20(elev_lowestmode).)
4A LiDAR
[GEDI L4A Footprint Level Aboveground Biomass Density, Version 2.1, https://doi.org/10.3334/ORNLDAAC/2056](https://daac.ornl.gov/cgi-bin/dsviewer.pl?ds_id=2056)

Height, canopy density and biomass are all interesting measures.
[Geo for Good 2021 : Novel Forest Data & Applications Part 1: GEDI & Obiwan - YouTube](https://www.youtube.com/watch?v=PQwVDnOsqhQ&list=WL&index=12)

![[Pasted image 20230818220321.png]]


## Statistical properties of hybrid estimators proposed for GEDI—NASA’s global ecosystem dynamics investigation - Patterson et al 2019


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


