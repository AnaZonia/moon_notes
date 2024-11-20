---
up:
  - "[[Rolling ideas]]"
stardate: Nov 17th 2024
update: Nov 17th 2024
dg-publish: true
---

Brian and Morgane used atmospherically corrected Landsat data to classify land use in Panama. Training data was not useful across footprints - training worked well for one footprint at a time only. I believe these are the reasons:
- Only Landsat's 9 bands were input into random forest. [[MAPBIOMAS]] seems to improve on this issue by ==using 90 features, and training the data for the whole country all at once, for each year==.
- Data for annual plants was implemented regardless of stage in growing cycle, but that should be considered for classification as MapBiomas [[Land Use#Time Series|does]]
- Rice and Citrus classes were classified using U-Net by MapBiomas

- [ ] Get landsat for Panama in the correct time window
- [ ] Collect some sample points for the main crop types of the country (perennial such as banana, annual such as maize, coffee)
- [ ] Can U-Net help us do better land use classification in Panama?
- [ ] Can Samgeo help us augment the datapoints for training?
- [ ] How to define the feature space for classification in Panama?
- [ ] Besides multispectral, could it be an advantage to add SAR data?
- [ ] How does time series help us classify, and how would we implement that?

