---
up: "[[001 The Bridge]]"
dg-publish: true
---
## Final products
- A land use classification map for Panama, dating back to 1985, including as many land use classes as possible and burned area. Uses methodology based on [[MAPBIOMAS]] and [[Cardille, Jeff]]'s regrowth/deforestation detection algorithm.
- A forest regrowth potential map for Panama, considering the effects of nitrogen fertilization as a predictor
- Expanding the probability of deforestation model that was already built for Panama, and incorporating it to the regrowth model to indicate areas of most promising regrowth in the country.

## Data available
- Paper on land use classification for Panama
- Paper on probability of deforestation
### Asner biomass data
Not necessarily comparable with ESA CCI Biomass for 2020. Airborne LiDAR for all of Panama, 2012. He may have more high resolution data for Panama.
### Jorge's model
Model on nutrient inputs for Panama. Surveyed over 100 farms on management and N fertilization practices. Found there is a strong relationship between regionality and crop type and nitrogen input. For land use classification, it would be good to know which land use types did he include so that they can be considered.
### Agua Salud - wet and dry plots
Managed by Jeff Hall. Long term data on forest biomass - useful to compare with ESA CCI, and compare how well our predictions do with better measured ground data.
The dry forest plots have not yet been used, and it would be nice to compare both wet and dry plots.

## Work plan

Brian and Morgane used atmospherically corrected Landsat data to classify land use in Panama. Training data was not useful across footprints - training worked well for one footprint at a time only. I believe these are the reasons:
- Only Landsat's 9 bands were input into random forest. [[MAPBIOMAS]] seems to improve on this issue by ==using 90 features, and training the data for the whole country all at once, for each year==.
- Data for annual plants was implemented regardless of stage in growing cycle, but that should be considered for classification as MapBiomas [[Land Use#Time Series|does]]
- Rice and Citrus classes were classified using U-Net by MapBiomas


### Land Use Classification Plan of Action
- [ ] Get landsat for Panama in the correct time window
- [ ] Collect some sample points for the main crop types of the country (perennial such as banana, annual such as maize, coffee)
- [ ] Can U-Net help us do better land use classification in Panama?
- [ ] Can Samgeo help us augment the datapoints for training?
- [ ] How to define the feature space for classification in Panama?
- [ ] Besides multispectral, could it be an advantage to add SAR data?
- [ ] How does time series help us classify, and how would we implement that?

## People
- [ ] Erika Berenguer
- [ ] [[Dent, Daisy]]
- [ ] [[Davies, Stuart]]
- [ ] Kendra Walker
- [ ] cara da silvicultura de Yale
- [ ] Kendra Walker - Land use map
- [ ] Elizabeth Goltz
- [ ] Jeff Hall (the email with Brian's 6k species paper and the STRI proposal)
- [ ] oswaldo - wanted help distinguishing between rice and other land use types
- [ ] Javier sanchez galan
- [ ] Milton Solano
- [ ] [[Ana Did Science Today#16/08, Fri - Meeting Jeff Hall with Brian|Jeff Hall]]
- [ ] Carmen - could she have more high-rez airborne data?


