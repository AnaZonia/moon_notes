---
up: "[[001 The Bridge]]"
dg-publish: true
---
Next point:
- lag may not be the same everywhere
	- is it variable by greeness?
	- model lag based on asymptote
	- comparisons of different datasets
- asymptote submodel (future climate change)
	- how can we predict changes in asymptote if drier/wetter places react differently to climate change?



### Fragmentation/human impact
Model probability of disturbance in Panama.

Examine disturbance of edge mature forests

get number of years of disturbance and deforestation before regrowth
does fire affect lag


- [ ] Time since burn
	- Time since last burn is very strongly correlated to number of burns, so it was removed. However, the time since each burn is probably relevant for regrowth, but I am not sure how to include this in the dataframe. For a patch that burned 5 times, or one that burned once, how do I incorporate that? should I make up to 33 columns - one with age for fire 1, other with age for fire 2, and so on?
- [ ] cabeças de gado por hectare
- [ ] pasto manejado ou pasto nativo
- [ ] [[SEBAL Evapotranspiration]] - evapotranspiration for Brazil







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




## Next steps
### Incorporate next variables
- [ ] Lençol freático
- [ ] [L-band vegetation optical depth (_L_-_VOD_)](https://ib.remote-sensing.inrae.fr/)
- [ ] [Species density](https://www.nature.com/articles/s41467-022-32063-z)

### Data analysis
- [ ] Compare age products
	- Celso's data was calculated until 2018
- [ ] Find MAPBIOMAS classification quality for the flooded forest class


- Older forests have less reliable biomass data - how can we correct for heteroskedasticity?

- Predict biomass of mature forests based on environmental predictors is a separate test that can also be done to find out whether that would make a better asymptote. Potentially a xgboost submodel would be helpful here.

- the relationships between the predictors may not be linear - this can be investigated through:
	- partial dependence plots
	- residual plots

since EU only has ages up until 1990 it would be useful to compare the same periods with mapbiomas



Northern Amazon is wetter, so it feels less the effect of fire. How does the model incorporate this knowledge?

[[Water Stress]] in the Amazonian context:
- The east and southeastern parts of the forest actually go months each year with little or no rain. The trees survive by tapping soil moisture as far down as 20 meters.


### Make final product
- [ ] Compare results with previous models
	- Show if there are fundamental differences between what the predictions would have been vs what they are now
		- get the key areas
		- absolute values (differences)
- [ ] Determine active vs. passive reforestation
	- Given the importance of surrounding forest cover, I should be able to determine how distance to mature forest can determine whether active or passive reforestation is recommended


## Model

## Introducing flexibility into k
- splines
- genetic algorithms
- neural networks
- hybrid models (XGBoost?)
- Mutual information  
- Late fusion
- Support Vector Machines

## Correcting censored data
- [ ] MCMC with STAN (+1000 chain length is unnecessary)
	- Can be hard to use discrete parameters
	- Values from HMC can be input into optim
	- [Bayesian in Python](https://towardsdatascience.com/how-to-use-bayesian-inference-for-predictions-in-python-4de5d0bc84f3)
- [ ] Hidden states/detection algorithm
- [ ] differentiating mature forests and fallow (everything that is mature from 1985 onwards)
## Parameter tuning
- [ ] [Theseus](https://sites.google.com/view/theseus-ai/)
- [ ] Evolution-based algorithms
	- [Generalized differential evolution](https://ieeexplore.ieee.org/document/8167916)
	- [Simulated Annealing](https://machinelearningmastery.com/simulated-annealing-from-scratch-in-python/)
		- [optim_sa](https://search.r-project.org/CRAN/refmans/optimization/html/optim_sa.html)
		- [anneal](https://search.r-project.org/CRAN/refmans/likelihood/html/anneal.html)
		- [from scratch](https://jmsallan.netlify.app/blog/coding-simulated-annealing-in-r/)