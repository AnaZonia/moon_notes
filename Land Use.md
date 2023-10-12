---
up:
  - "[[110 Remote Sensing]]"
stardate: Oct 7th 2023
update: Oct 7th 2023
share_link: https://share.note.sx/dghdlzp7#8exGPa+qTLGQqxjdJu0fTf4YS9eKU3rxp54YeZrs9k8
share_updated: 2023-10-11T19:19:10-04:00
---
## How does MapBiomas do it?
Here I write a short summary of [ATBD Collection 8 MapBiomas](https://brasil.mapbiomas.org/wp-content/uploads/sites/4/2023/09/ATBD-Collection-8-v1.1.docx.pdf) and [ATBD MapBiomas Amazonia 4.0](https://s3.amazonaws.com/amazonia.mapbiomas.org/atbd/atbd%20general/ATBD_General_MapBiomas_Amazonia_4.0.pdf)including necessary Appendix info. 

[MapBiomas Brasil Github](https://github.com/mapbiomas-brazil) has the source code:
- JS - image classification and post-classification
- Python API - Map integration, post-classification, statistical analysis
- R - improve processing of large datasets, machine learning, data analysis and visualization.

### MapBiomas Brasil
Using Surface Reflectance (SR) from Landsat Collection 2 (Tier 1) 


1. Got landsat data in specific temporal windows to optimize spectral contrast and better discriminate the LULC classes (t0 and t1 in day/month/year)
2. Define feature spaces for each year
	- Shadow masking + cloud cover less than or equal to 50%
		- Temporal Dark Outlier Mask (TDOM) algorithm (is that the GEE median reducer - which picks the median pixel value in each band over time?)
		- Band Quality Assessment (BQA)
		- Visually removed scenes that could affect results like haze, cloud, no data through a preview on earth engine


![](https://imgur.com/fW0m717.png)

- Trained with samples produced by LAPIG/UFG [Chave de Interpretação](https://chave.lapig.iesa.ufg.br/pt/) and then ran [data augmentation](https://www.datacamp.com/tutorial/complete-guide-data-augmentation)
1. Yearly training samples for each biome

![](https://imgur.com/RU2OTOP.png)

#### Amazonia Bioma
![](https://imgur.com/tUX4UZg.png)

[Using the U‐net convolutional network to map forest types and disturbance in the Atlantic rainforest with very high resolution images (Wagner et al 2019)](https://zslpublications.onlinelibrary.wiley.com/doi/epdf/10.1002/rse2.111)


### Mapbiomas Amazonas (RAISG)
==Red Amazónica de Información Socioambiental Georreferenciada (RAISG)==

![](https://imgur.com/PmkHtb5.png)

![](https://imgur.com/bn3Iym5.png)
### Land use classification
![](https://imgur.com/O6bdGWO.png)

![](https://i.imgur.com/S5doCrT.png)


### U-Net
[Working with U-net in R (github)](https://github.com/JonathanVSV/U-netR)
There's a possibility that combining with SAR for the classification will be even better - but does that mean that using SAR as response will become redundant as far as the stats goes?
[Land Use Land Cover Classification with U-Net: Advantages of Combining Sentinel-1 and Sentinel-2 Imagery](https://www.mdpi.com/2072-4292/13/18/3600#)

![](https://www.mdpi.com/remotesensing/remotesensing-13-03600/article_deploy/html/images/remotesensing-13-03600-g002.png)



### Time Series
For mapping annual crops, the Landsat mosaics require images that cover the period from October to March

[F4 - Earth Engine Fundamentals and Applications - EEFA - Live Document - Google Docs](https://docs.google.com/document/d/11oo1TuvXyEvReoYLDeTcoh16rEN90I8Bf5qp0KxVu7U/edit) (page 109)


### Desmatamento/Vegetação Secundária

[Benchmark maps of 33 years of secondary forest age for Brazil (Silva Junior 2020)](https://www-nature-com.proxy3.library.mcgill.ca/articles/s41597-020-00600-4)

## Samgeo
*A Python package for segmenting geospatial data with the Segment Anything Model (SAM)* - Automatically generates masks
May help with the collection of training data?
[documentation](https://samgeo.gishub.org/)
[github](https://github.com/opengeos/segment-geospatial)
[paper](https://joss.theoj.org/papers/10.21105/joss.05663)

![](https://camo.githubusercontent.com/32f6f9e30c7f773b42e7c7d6c47a251b88e88723af456afd8016c26063966204/68747470733a2f2f692e696d6775722e636f6d2f4931496844677a2e676966)
## Other efforts
[The Global 2000-2020 Land Cover and Land Use Change Dataset Derived From the Landsat Archive: First Results (Potapov 2022)](https://www.frontiersin.org/articles/10.3389/frsen.2022.856903/full) did a global analysis of multiple types of land use change, but did not go further than "cropland" class.

[CERES: IGBP Land Classification | Climate Data Guide (ucar.edu)](https://climatedataguide.ucar.edu/climate-data/ceres-igbp-land-classification)
There are issues with shrubland classification in Panama, they are often misclassified as secondary forests.

Another algorithm that flags deforestation events 
AVOCADO [Continuous monitoring of forest change dynamics with satellite time series (Decuyper 2022)](https://www.sciencedirect.com/science/article/pii/S0034425721005496?via%3Dihub)
What does it add to previous algorithms? 

- captures gradual change (unlike rgrowth, for example) 

- would be possible to incorporate logging for example 

- is less effective on dry tropical forest because NDMI of crops is quite similar to NDMI of the forest itself... so be careful with that. Regrowth was flagged accidentally. 

Some sociological factor studies only show the probability of permanence of forests depending on different sociological factors; forests may be allowed to regrow for 5-20 years before being cleared up again. This could just be a predictor for fallow period, but that’s gathered from remote sensing anyways, so it’s kind of useless for my study. 

The algorithm is calibrated with nearby mature forests.

[rgrowth - Tracking disturbance-regrowth dynamics (bendevries.ca)](http://bendevries.ca/rgrowth/)