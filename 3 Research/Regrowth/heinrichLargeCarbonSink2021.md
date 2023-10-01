  
---
aliases: ["Large carbon sink potential of secondary forests in the Brazilian Amazon to mitigate climate change"] 
year: 2021 
first-author: Heinrich, Viola H. A.
publisher: "Nature Communications" 
tags:   #number_one   
url: https://www.nature.com/articles/s41467-021-22050-1 
type: lit_note
at-a-glance: "Separated plots by category, used ESA biomass and mapbiomas to calculate mean AGBD per age"

--- 
authors: [[Heinrich, Viola H. A.]], [[Dalagnol, Ricardo]], [[Cassol, Henrique L. G.]], [[Rosan, Thais M.]], [[De Almeida, Catherine Torres]], [[Silva Junior, Celso H. L.]], [[Campanharo, Wesley A.]], [[House, Joanna I.]], [[Sitch, Stephen]], [[Hales, Tristram C.]], [[Adami, Marcos]], [[Anderson, Liana O.]], [[Aragão, Luiz E. O. C.]]

[[010 Amazonia MOC]]

**Bibliography:** Heinrich, Viola H. A., Ricardo Dalagnol, Henrique L. G. Cassol, Thais M. Rosan, Catherine Torres De Almeida, Celso H. L. Silva Junior, Wesley A. Campanharo, et al. ‘Large Carbon Sink Potential of Secondary Forests in the Brazilian Amazon to Mitigate Climate Change’. _Nature Communications_ 12, no. 1 (19 March 2021): 1785. [https://doi.org/10.1038/s41467-021-22050-1](https://doi.org/10.1038/s41467-021-22050-1). 

>[!summary] Summary
> 


<p>  <span style="color: #F9E076">Identifying the proximity of secondary forests to disturbed versus undisturbed forests could potentially be another driving variable impacting the regrowth rates we have calculated in this study.</span>  </p> <p>  <span style="color: #F9E076">Only areas of secondary forest greater than 9000 m2 were considered for further analysis, an area approximately equal to 1 pixel of the ESA-CCI product.</span>  </p> <p>  <span style="color: #F9E076">Mean annual downward shortwave radiation</span>  </p> <p>  <span style="color: #F9E076">Maximum Cumulative Water Deficit (MCWD)</span>  </p> <p>  <span style="color: #F9E076">The drivers were then grouped according to numerical limits, such as the 25, 50 and 75th percentiles. We then modelled the AGC for the age of secondary forest under these groupings using the commonly used Chapman-Richard model for regrowth67:</span>  </p> <p>  <span style="color: #F9E076">The “cforest” random-forest model provides more accurate importance estimates compared to more traditional random-forest models such as “randomForest” when the dataset includes both</span>  </p> <p>  <span style="color: #F9E076">MCWD</span>  </p> <p>  <span style="color: #F9E076">Identifying the proximity of secondary forests to disturbed versus undisturbed forests could potentially be another driving variable impacting the regrowth rates we have calculated in this study.</span>  </p> <p>  <span style="color: #F9E076">Only areas of secondary forest 9000 m2 greater than were considered for further analysis, an area approximately equal to 1 pixel of the ESA-CCI product.</span>  </p> <p>  <span style="color: #F9E076">Mean annual downward shortwave radiation</span>  </p> <p>  <span style="color: #F9E076">Maximum Cumulative Water Deficit (MCWD)</span>  </p> <p>  <span style="color: #F9E076">The drivers were then grouped according to numerical limits, such as the 25, 50 and 75th percentiles. We then modelled the AGC for the age of secondary forest under these groupings using the commonly used Chapman-Richard model for regrowth67:</span>  </p> <p>  <span style="color: #F9E076">The “c “cforest” random-forest model provides more accurate importance estimates compared to more traditional random-forest models such as “r “randomForest” when the dataset includes both c</span>  </p> <p>  <span style="color: #F9E076">MCWD</span>  </p> 
 

>CWD is a measure of water availability: Potential Evapotranspiration minus Actual Evapotranspiration (PET  AET) and is an indicator of prolonged drought. 


Secondary growth rates vary in different regions of the amazon due to environmental heterogeneity and post-succession disturbance 

the relationship between secondary forest regrowth and environmental and disturbance drivers has never been explored spatially explicitly using global remote sensing products.

Secondary forests uptake more carbon than primary. Carbon sequestration in the west is higher than in the east (phosphorus may matter here?). Carbon stocks could be higher with less fire and deforestation. Carbon stocks are lower in regions with water deficit. Deforestation of secondary forests means 70% of amazon forest loss. 

However, the relationship between secondary forest regrowth and environmental and disturbance drivers has never been explored spatially explicitly using global remote sensing products. 

Spatial variation in secondary forest regrowth – this article shows the differences in growth rates among the amazon basin due to natural factors (precipitation, soil moisture, shortwave radiation). 

- Expect higher regrowth in the north.
- Importance of fire and deforestation varies with the region - fires disturb wet forests less.

Species in secondary growth forests have smaller seeds and lower wood density. 

There is fire and deforestation that happen after regrowth has already begun, and that changes regrowth rates the most. Proximity to other forests could also make a difference (seed bank). Would be interesting to look at spatial heterogeneity in the process. 

DATA

- Santoro
- Mapbiomas
- Modelled through Chapman Richards

Divided the Amazon in three climatic zones rather than seeing climate as a continuous variable.

- Radiation
- Precipitation
- Maximum cumulative water deficit
- Soil cation concentration as a proxy for fertility
- Burned area (MODIS, Terra - Didan 2015)
- Number of deforestations

Data availability

The original data used in this study are all publicly available from their sources:

MapbiomasV3.1 ([https://mapbiomas.org/](https://mapbiomas.org/)); ESA-CCI Aboveground Biomass for the year

2017 ([https://catalogue.ceda.ac.uk/uuid/bedc59f37c9545c981a839eb552e4084](https://catalogue.ceda.ac.uk/uuid/bedc59f37c9545c981a839eb552e4084)); CHIRPS

precipitation data: [Funk](https://www.nature.com/articles/sdata201566) et al.27—https://edcintl.cr.usgs.gov/downloads/sciweb1/shared/

fews/web/global/monthly/chirps/final/downloads/monthly/); Soil Cation Concentration

data: Zuquim et al.30—https://doi.pangaea.de/10.1594/PANGAEA.879542; Shortwave

radiation data: TerraClimate, Didan31, [http://www.climatologylab.org/terraclimate.html](http://www.climatologylab.org/terraclimate.html).

The MCWD data can be produced using data from Funk et al. combining with code

available from Campanharo and Silva Junior66—https://zenodo.org/record/2652658#.

X9CV-aFxdPY. The processed data and products produced in this research are available

on the following repository: [https://zenodo.org/record/4479234#.YBVdBHNxdPY75](https://zenodo.org/record/4479234#.YBVdBHNxdPY75). The

regrowth models can be built by users using Equation 1 in the methods section and

information provided in Supplementary Tables 8 and 9 and the shapefiles corresponding

to the four climate regions are available in the aforementioned repository. Additional

map data, namely the Amazon biome region and country vector shapefiles are available

from the following two sources, respectively: [http://terrabrasilis.dpi.inpe.br/en/homepage/](http://terrabrasilis.dpi.inpe.br/en/homepage/)

and [https://www.naturalearthdata.com/downloads/10m-physical-vectors/10mland/](https://www.naturalearthdata.com/downloads/10m-physical-vectors/10mland/).

Finally, the TerraClass land-cover dataset is available from: [https://www.terraclass](https://www.terraclass).

gov.br/. Source data are provided with this paper.


%% Import Date: 2023-09-30T21:31:40.716-04:00 %%
