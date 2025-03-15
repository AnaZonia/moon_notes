---
up:
  - "[[000 Chapter 1 - Predicting Regrowth in Brazil]]"
stardate: Nov 17th 2024
update: Nov 17th 2024
dg-publish: true
---
Biomass data




### Land use
- number of years under fallow
- time since last fire
- total number of fires
- total years under each land use type
- last observed land use type
### Landscape
- soil type ([[FAO Soil Map of the World]], [[Zuquim 2023 - Introducing a map of soil base cation concentration, an ecologically relevant GIS-layer for Amazonian forests|Zuquim]], [[SoilGrids]])
- protected areas
- indigenous areas
- [[Ecoregions]]
- surrounding forest biomass (mature forest cover)
	- mean forest biomass per ecoregion
### Climatic (yearly)
[[002 Data Sources#Climate|Climate Data Sources]]
- [[Seasonality]]
- mean annual precipitation
- [[Evapotranspiration]]
- [[Latent Heat Flux]]
- [[Cumulative Water Deficit]]

## Workflow
### Step 0: Data gathering

#### Aggregating land use types
Land use can be described with all categories provided by MapBiomas:
- 3 = forest
- 15 = pasture
- 39 = soy
- 20 = sugar cane
- 21 = mosaic of uses
- 40 = rice
- 62 = cotton
- 41 = other temporary crop
- 46 = coffee
- 47 = citrus
- 35 = palm oil
- 48 = other perennial crop
- 9 = forest plantation

 Or aggregated into fewer categories.:
- annual_crops = 39, 20, 40, 62, 41
- perennial_crops = 46, 47, 35, 48
- pasture = 15
- mosaic = 21
- forest plantation = 9

This will tell whether there is an improvement in predictive power by increasing number of categories. It can be useful to determine how many classes do we need to distinguish between when doing land use classification.
#### Land Use Intervals
Since we only have data until 1985, we have **censored data** - we know less land use history information about older forests than younger forests. If a forest is 30 years old,

**1985** ---- 5 years ---- **1990** ------------- 30 years ------------**2020**

Its land use history information will be less representative than that of a 5 year old forest,

**1985** ------------- 30 years ------------ **2015** ---- 5 years ---- **2020**

To correct for this, we select the data between *land use intervals* - 5, 10 or 15. There are two ways of doing this:
- **Max_limit:** Find what is the time between first and last year of anthropogenic land use in each pixel. If this time interval is less than or equal to the desired land use interval, that pixel is kept - otherwise, it is excluded.
	For example, for a pixel in which the first year with observed anthropogenic land use is 2001, and last is 2010, after which the land regrows:
		
	**1985** -------- **2001** ---- 9 years ---- **2010** -------- **2020**

	The time interval is 9 years, so this pixel is present in the data under the 10 and 15 year limits.

- **Hard_cut:** Independently of the first and last year of observed anthropogenic land use, the land use history is restrained to a hard cut of 5, 10 or 15 years.
		Say, for a pixel that regrows after 2010:
	
	**1985** ----------------- **2016** ---- 5 years ---- **2010** -------- **2020**
	**1985** ------------ **2001** ------ 10 years ------ **2010** -------- **2020**
	**1985** -------- **1996** -------- 15 years -------- **2010** -------- **2020**

*Note*: This will restrain the age range present. For example, if we have a fixed 10 years of history:
**1985** ----- 10 years ----- **1995** ------------- 25 years ------------**2020**
The regrowing forests have started regrowing in 1995 at the very earliest.

#### Age data sources
There are two sources of age data from Landsat going back to 1985 - Mapbiomas, made for the Brazilian territory, and TMF Ages, made by the European Union for the world. TMF ages considers phenology, flagging disturbance as well as deforestation. Also, since it is international, it opens the possibility of fitting the model to Panama right away.

#### Multicollinearity
Tested for multicollinearity. Removed columns that show multicollinearity, mostly environmental ones. Also showed strong multicollinearity:
- time since last fire

#### First fit comparison - machine learning, ages, biome
The first step is to compare machine learning methods as a reference point for the process-based model.

├── Comparisons:
│   ├── Machine Learning:
│   │   ├── XGBoost
│   │   ├── LM
│   │   └── Random Forest
│   ├── Biome:
│   │   ├── Amazon (1)
│   │   ├── Atlantic Forest (4)
│   │   └── Both
│   └── Age data source:
│       ├── Mapbiomas
│       └── EU

For this, we include all environmental predictors. Land use is only considered for MapBiomas, with no land use aggregation or land use history interval subsetting.

- Import data.
	- Categorical variables are converted, and categories with less than 500 occurrences are excluded.
	- For MapBiomas data, stratified sampling - ensures that rare categories are properly represented, and eliminates categories with too few data points to be considered. This makes it so that some land use categories that are found in one biome but not in the other are incorporated or excluded appropriately.
	- Two data frames are exported:
		- data, with 10,000 rows
		- data_unseen, with 2,000 rows
- for XGBoost and Random Forest, initial grid search is conducted on hyperparameters.
- Data is split into 5 for 5-fold cross-validation, and max_min normalization is conducted on each fold after splitting. The best model out of the 5 is then applied to unseen data. The average R2 across the 5 folds and the R2 on the final validation on unseen data are output.

![](https://i.imgur.com/8MJ7fhR.png)

Conclusions:
- XGBoost is the best machine learning method for future comparisons.
- The Atlantic Forest and the Amazon should be fit separately.
- The Atlantic Forest has higher R2 values, likely due to the fact that it has more varied land use types which have high feature importance.
- EU ages seemed to correspond better with biomass than Mapbiomas ages:

├── Correlation:
│   ├── Atlantic Forest:
│   │   ├── Correlation between age sources: 0.41
│   │   ├── R2 lm(biomass ~ age_mapbiomas): 2.5%
│   │   └── R2 lm(biomass ~ age_eu): 5%
│   └── Amazon:
│      ├── Correlation between age sources: 0.66
│      ├── R2 lm(biomass ~ age_mapbiomas): 3.7%
│      └── R2 lm(biomass ~ age_eu): 6%

Still, since the EU data was fit with the machine learning models without taking into consideration fire or land use, while mapbiomas did have fire and land use history considered, Mapbiomas data had higher R squared values across all biomes, especially in the Atlantic Forest, where land use history is expected to be a more important predictor.

#### Second fit comparison: land use aggregation, land use intervals, clipping method

Using XGBoost, with Atlantic Forest Biome only,

- test whether blunt cut or max limit is best (non_aggregated only).
avg blunt cut vs max limit across land use intervals (5, 10, 15) - 3 values

├── Environmental + Land Use (Mapbiomas, Atlantic Forest)
│   ├── Land-Use Intervals:
│   │   ├── All
│   │   ├── 5
│   │   ├── 10
│   │   └── 15
│   ├── Method of clipping intervals:
│   │   ├── Blunt Cut
│   │   └── Max Limit
│   ├── Data aggregation:
│   │   ├── Aggregated
│   │   └── Non-Aggregated

- test whether aggregated or non_aggregated is best
avg aggregated vs non_aggregated across land use intervals (5, 10, 15) with the preferred cutting method


### Step 1: Compare Process-Based Models

The best initial k0 is derived from the main equation:
k0 = -np.log(1 - (y.mean() / A.mean()))

  ├── Parameter Combination: [age, surrounding_cover]
  ├── Biome: Amazon
  ├── Fitting Method: NLL
  └── Non-Aggregated
       └── Process-Based Model:
           ├── B0_theta
           ├── Lag + fit k
           ├── Lag + fit A
           └──Lag + fit k + fit A
               ├── Parameter Combinations:
                   ├── Environmental
                   ├── Environmental + Land Use (Mapbiomas)

### Step 3: Compare Climate History (Using Preferred Land Use Method)
  ├── Brazil
  │   ├── Biomes:
  │   │    ├── Amazon
  │   |    ├── Atlantic Forest
  │   |    └── Both 
  │   |        ├─ No Climate History
  │   |        └─ Climate History 
  |
  └─ Panama 
      └─ Environmental + Fire (EU)
          ├─ No Climate History 
          └─ Climate History 

