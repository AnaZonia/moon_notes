---
up: 
stardate: Jun 4th 2024
update: Jun 4th 2024
dg-publish: true
---
Modelling Neotropical Forest Regrowth: The Role of Land Use History

**The future of tropical forests relies not only on the conservation of old growth, but also on the regeneration of deforested land.** Currently, about one-third of anthropogenic carbon emissions are offset by terrestrial ecosystems, mainly forests1. However, the significant role of secondary forests in this crucial process often remains overlooked. Secondary forests, comprising over half of tropical forests today2, not only exhibits carbon sequestration rates up to 20 times faster than mature forests during succession3, but also prevents nutrient loss by erosion4, preserves watersheds4, and shelters biodiversity5. Considering the urgent demand for immediate climate action, in addition to halting deforestation, it is imperative to that we understand the processes regulating secondary forest regrowth to set accurate climate targets and reverse land degradation as effectively as possible.

**Accurate carbon sequestration estimates are required to set climate targets, but much variability in regrowth trajectories is still unexplained by existing predictive models.** Previous modelling efforts have emphasized broad environmental drivers such as water stress2, but have not yet addressed many of the more nuanced ecological and environmental interactions that might also significantly affect regrowth6. Also, until recent technical advances, growth estimates were restricted to individual plots, hindering the generalizability of models to broader scales encompassing undersampled locations.

**To improve the accuracy of regrowth predictions, models need to go beyond broad environmental drivers to explicitly incorporate the effects of land use history.** Land use history can significantly affect rates of forest regeneration, a particularly crucial consideration in heavily agricultural Latin America. One third of all Neotropical forests are regrowing on land previously occupied by agriculture7. Previous research has shown that land management practices can have diverse and lasting effects on soil health. For instance, burning can volatilize nitrogen and deplete the soil's seedbank and microbiota9; heavy machinery can compact the soil, reducing root growth and water infiltration7; and pastureland can introduce invasive grasses which inhibit the establishment of native seedlings9. Erosion caused by agriculture can increase phosphorus loss, a limiting nutrient in tropical soils10; still, allowing for fallow periods can support the replenishment of nitrogen and other nutrients8. Previous studies have called for more detailed descriptions of land use history3 in estimates of forest regrowth, particularly at large scales where quantifying nutrient pools directly is impractical.

Modern remote sensing tools have recently made it feasible to construct such ambitious large-scale models. In 2015, Brazil launched MAPBIOMAS16, the first initiative to create a country-wide land use history map, which is under continued development. This exceptional dataset distinguishes the main crop types, illustrating the nuances of agriculture beyond the simple crop/pasture categorization, and sets a precedent for the quality of land use classification that can be done with Landsat data (which extends back to 1985) in other Latin American countries. Also, a previous study done by a STRI fellow [Walker 2020] has conducted land use classification for Panama, distinguishing between forest age classes, (low vegetation (1-2 years old), medium (3–5 years old), high (6–20 years old) and forest (≥ 20 years old)), as well as for some land use classes. The past years have also seen new technology that allows for large-scale aboveground biomass maps. ESA’s Biomass Climate Change Initiative17 launched worldwide biomass data products after 2015, and Panama has the first country-wide carbon map done by aerial LiDAR in 2012. These initiatives provide unprecedented, extensive information on the history and biomass of Neotropical forests, which are central to climate change mitigation. Given its extensive secondary forests17 and availability of new data spanning large spatial and temporal extents, Panama now presents a unique opportunity to integrate over 30 years of land use history into tropical forest regrowth modelling. This not only holds the potential to provide valuable insights for the Panamanian context, but also opens doors to explore the scalability of these approaches to other tropical countries facing similar challenges.


|                                       | Product Type                      | Year of Launch | Years of data available |
| ------------------------------------- | --------------------------------- | -------------- | ----------------------- |
| MAPBIOMAS                             | Landsat (Optical)                 | 2015           | 1985-2024               |
| GEDI                                  | LiDAR                             |                |                         |
| ESA Biomass Climate Change Initiative | SAR with LiDAR calibration (GEDI) |                |                         |
| Asner                                 | Airborne LiDAR                    | 2012           |                         |




With this research project, I am modelling the regrowth trajectory of Panamanian forests. To do this, I (1) Classify land use history in Panama, (2) Model regrowth in Panama, (4) Incorporate predictions of secondary forest persistence, and (4) Validate model results with Agua Salud data.

Aim 1 – Build Panama-wide land use history maps. Using as reference the methodology from MAPBIOMAS, which generated annual maps in South America, I will build land use maps in Panama from 1985 to 2024. This will require manual selection of training classification data with high-resolution remote sensing imagery, cleaning of Landsat data, and implementation of a Random Forest algorithm. Given that the already existing 5 land use history maps for Panama spanning 3–4-year composites from 1985 to 2016 do not distinguish between crop types, but do identify age classes in the regrowth trajectory, their methodology will be implemented to identify forest ages, using the same Landsat data, run through a decision tree. Both methodologies will be cross compared to ensure the highest accuracy is achieved. Fire history will be also obtained with MAPBIOMAS methods and Landsat normalized burn ratio.

Aim 2 - Modelling regrowth in Panama. I am building a semi-mechanistic growth model based on the well-established Chapman-Richards3 growth curve (Fig. 1). Using a space-for-time chronosequence, I fit the growth rate and asymptote by incorporating (1) environmental descriptors such as water deficit and soil type, (2) fire history (time since last burn, number of burns), (3) land use type within 33 years of history, and (4) distance to nearest mature forest. With biomass data from the ESA CCI Biomass initiative, we can explain the carbon accumulation potential in land abandoned by agriculture, generating the most complete forest regrowth model to date.

Aim 3 – Incorporating secondary forest persistence. A previous study conducted in partnership with Jeff Hall at STRI18, has built a map of secondary forest persistence for Central Panama, predicting the odds that a forest will be allowed to regrow considering anthropogenic predictors such as its distance to urban areas and roads. I will replicate this study for the entire country of Panama, following the methodology described in the paper and openly available data. In conjunction with the regrowth potential model, this map would allow for a more complete prediction of regrowth potential by incorporating the probability of human interference, a very important metric that otherwise would be left ignored. The final product would be a Panama-wide map for forest regrowth potential based on environmental factors, land use history, and probability of human disturbance.

Aim 4 – Validating results with Agua Salud data. Agua Salud provides a unique opportunity to validate satellite-based predictions with long-term regeneration data. While the remote sensing work can be started in Canada, being able to conduct the research closely with the supervision of Dr. Jeff Hall would be invaluable for this project, due not only to his involvement with the secondary forest persistence model and long-term experience with forest regrowth, but also due to the access of the only long-term forest regrowth experiment that would allow for ground-truthing of the satellite-based predictions. By spending a week directly working at the Agua Salud field plots, I could better visualize the varying trajectories of forest regrowth and investigate if there are any notable discrepancies that would have ecological significance but not be well represented by the model predictions. Also, Agua Salud’s biomass data can be compared to model predictions for a unique opportunity to compare expected and observed values.

Outcomes – With open access remote sensing data, we can create an open-source product that can be easily leveraged to policy. By improving our current ability to predict the regrowth potential of deforested land with diverse histories, we can make better informed decisions when establishing new protected areas and planning carbon sequestration strategies.
