---
up: "[[001 The Bridge]]"
dg-publish: true
---
## Final products
- A land use classification map for Panama, dating back to 1985, including as many land use classes as possible and burned area. Uses methodology based on [[MAPBIOMAS]] and [[Cardille, Jeff]]'s regrowth/deforestation detection algorithm.
- A forest regrowth potential map for Panama, considering the effects of nitrogen fertilization as a predictor
- Expanding the probability of deforestation model that was already built for Panama, and incorporating it to the regrowth model to indicate areas of most promising regrowth in the country.

## Agriculture expertise

Nitrogen data, but how much can we infer from land use practices in Panama. What kind of data could I use that I may not have considered yet?


## Data available
- Walker et al 2020 - Capturing ephemeral forest dynamics with hybrid time-series and composite mapping in the Republic of Panama
- Bardino et al 2023 - Landscape context importance for predicting forest transition success in central Panama
- Fires, land use

put the 1990s land use stuff in snowi:/home/shared/svaradarajan/landuse1990s. It's global so you'll have to crop it to whichever country.

And here's the paper: [https://www.tandfonline.com/doi/pdf/10.1080/014311600210209](https://can01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.tandfonline.com%2Fdoi%2Fpdf%2F10.1080%2F014311600210209&data=05%7C02%7Cana.avila%40mail.mcgill.ca%7C11adce861b0f429e09a408dccc6b4e11%7Ccd31967152e74a68afa9fcf8f89f09ea%7C0%7C0%7C638610008432920320%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C0%7C%7C%7C&sdata=sBVDK1A0LaaCM6mYWo%2Fto4IfFd6rA5kmjKeCXHq372Q%3D&reserved=0 "Original URL: https://www.tandfonline.com/doi/pdf/10.1080/014311600210209. Click or tap if you trust this link."). I don't have a file for the lookup table of values but the figure description on page 1351 has all of them.


With what we have right now, we can have a preliminary map of regrowth potential for Panama.
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
- [ ] Elizabeth Goltz
- [ ] Jeff Hall (the email with Brian's 6k species paper and the STRI proposal)
- [ ] oswaldo - wanted help distinguishing between rice and other land use types
- [ ] Javier sanchez galan
- [ ] Milton Solano
- [ ] [[000 Ana Did Science Today#16/08, Fri - Meeting Jeff Hall with Brian|Jeff Hall]]
- [ ] Carmen - could she have more high-rez airborne data?
- [ ] [[Slusser, Jacob]]
- [ ] Helena Muller Landau

