---
up: "[[001 The Bridge]]"
stardate: Aug 18th 2023
update: Nov 24th 2023
dg-publish: true
---
[[Model Overview]]

## Workflow
### Step 0: Data gathering

#### Aggregating land use types
Land use can be described with all categories provided by MapBiomas, or aggregated into fewer categories.


#### Land Use Intervals



results_df has results for non_aggregated, max_limit, all land use intervals
it shows that amazon and atlantic forest fit best in separation


for each model, get average r2 across all biomes and data sources

  ├── Test Performance on:
  │   ├── Machine Learning:
  │   │   ├── XGBoost
  │   │   ├── LM
  │   │   └── Random Forest
  xgboost is best

  ├── Brazil

  │   │   ├── Atlantic Forest
  │   │       ├── Parameter Combinations:
  │   │       │   ├── Environmental + Land Use (Mapbiomas)
  │   │       │   │   ├── Land-Use Intervals:
  │   │       │   │   │   ├── All
  │   │       │   │   │   ├── 5
  │   │       │   │   |   |   ├── Aggregated
  │   │       │   │   |   |   └── Non-Aggregated:
  │   │       │   │   |   |       ├── Blunt Cut
  │   │       │   │   |   |       └── Max Limit
  │   │       │   │   │   ├── 10
  │   │       │   │   |   |   ├── Aggregated
  │   │       │   │   |   |   └── Non-Aggregated
  │   │       │   │   |   |       ├── Blunt Cut
  │   │       │   │   |   |       └── Max Limit
  │   │       │   │   │   └── 15
  │   │       │   │   |       ├── Aggregated
  │   │       │   │   |       └── Non-Aggregated:
  │   │       │   │   |           ├── Blunt Cut
  │   │       │   │               └── Max Limit
  │   │       │   ├── Environmental (Mapbiomas)
  │   │       │   └── Environmental (EU)
  └── Panama
      └── Environmental + Fire (EU)

15 data combinations per biome. 30 data combinations.

xgboost
atlantic forest only
- test whether blunt cut or max limit is best (non_aggregated only).
avg blunt cut vs max limit across land use intervals (5, 10, 15) - 3 values

- test whether aggregated or non_aggregated is best
avg aggregated vs non_aggregated across land use intervals (5, 10, 15)


heatmap, correlation matrix, multicollinearity
- amazon and atl for in isolation fit better than together


### Step 1: Compare Models

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
           ├── Lag + fit k + fit A
           └── k0 = -np.log(1 - (y.mean() / A.mean()))
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


#### Incorporating climate history
$$
\mathrm{AGB}=A \cdot (1-\underbrace{e^{-k} \cdot e^{-k} \cdots \cdot e^{-k} \cdot e^{-k}}_{t \text { times }})^\tau
$$
$$
\mathrm{AGB}=A \cdot \left(1-\left(e^{-k_1} \cdot e^{-k_2} \cdot \cdots \cdot e^{-k_{t-1}} \cdot e^{-k_t}\right)\right)^\tau=
$$
$$
\mathrm{AGB}= A \cdot \left(1-e^{-k t}\right)^\tau
$$
$$ 
\mathrm{AGB} = A \cdot \left(1-\prod_{t=1}^{t_\text{max}}e^{- (E_t+LU)}\right)^\tau
$$
$$
\mathrm{AGB} = A \cdot \left(1-e^{-\sum_{t=1}^{t_\text{max}} (E_t+LU)}\right)^\tau
$$



## Next steps
### Incorporate next variables
- [ ] Lençol freático
- [ ] Time since burn
	- Time since last burn is very strongly correlated to number of burns, so it was removed. However, the time since each burn is probably relevant for regrowth, but I am not sure how to include this in the dataframe. For a patch that burned 5 times, or one that burned once, how do I incorporate that? should I make up to 33 columns - one with age for fire 1, other with age for fire 2, and so on?
- [ ] [L-band vegetation optical depth (_L_-_VOD_)](https://ib.remote-sensing.inrae.fr/)
- [ ] [Species density](https://www.nature.com/articles/s41467-022-32063-z)
- [ ] cabeças de gado por hectare
- [ ] pasto manejado ou pasto nativo

### Data analysis
- [ ] Compare age products
	- Celso's data was calculated until 2018
- [ ] MAPBIOMAS classification quality - flooded forest class

 Examine disturbance of edge mature forests
 
get number of years of disturbance and deforestation before regrowth

- Older forests have less reliable biomass data - how can we correct for heteroskedasticity?

- Predict biomass of mature forests based on environmental predictors is a separate test that can also be done to find out whether that would make a better asymptote. Potentially a xgboost submodel would be helpful here.
- the relationships between the predictors may not be linear - this can be investigated through:
	- partial dependence plots
	- residual plots

since EU only has ages up until 1990 it would be useful to compare the same periods with mapbiomas

Remake this plot for EU data

![[Chapter 1 - Predicting Regrowth in the Amazon.png]]

### Try new optimizers
#### Correcting censored data
- [ ] MCMC with STAN (+1000 chain length is unnecessary)
	- Can be hard to use discrete parameters
	- Values from HMC can be input into optim
	- [Bayesian in Python](https://towardsdatascience.com/how-to-use-bayesian-inference-for-predictions-in-python-4de5d0bc84f3)
- [ ] Hidden states/detection algorithm
- [ ] differentiating mature forests and fallow (everything that is mature from 1985 onwards)
#### Parameter tuning
- [ ] [Theseus](https://sites.google.com/view/theseus-ai/)
- [ ] Evolution-based algorithms
	- [Generalized differential evolution](https://ieeexplore.ieee.org/document/8167916)
	- [Simulated Annealing](https://machinelearningmastery.com/simulated-annealing-from-scratch-in-python/)
		- [optim_sa](https://search.r-project.org/CRAN/refmans/optimization/html/optim_sa.html)
		- [anneal](https://search.r-project.org/CRAN/refmans/likelihood/html/anneal.html)
		- [from scratch](https://jmsallan.netlify.app/blog/coding-simulated-annealing-in-r/)
	
### Make final product
- [ ] Compare results with previous models
	- Show if there are fundamental differences between what the predictions would have been vs what they are now
		- get the key areas
		- absolute values (differences)
- [ ] Determine active vs. passive reforestation
	- Given the importance of surrounding forest cover, I should be able to determine how distance to mature forest can determine whether active or passive reforestation is recommended
- [ ] Make a confidence metric map
