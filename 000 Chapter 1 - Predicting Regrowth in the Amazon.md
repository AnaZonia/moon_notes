---
up: "[[001 The Bridge]]"
stardate: Aug 18th 2023
update: Nov 24th 2023
dg-publish: true
---
## Predictors

### Land use
- number of years under fallow
- time since last fire
- total number of fires
- total years under each land use type
- last observed land use type

### Landscape
- soil type ([[FAO Soil Map of the World]], [[Zuquim 2023 - Introducing a map of soil base cation concentration, an ecologically relevant GIS-layer for Amazonian forests|Zuquim]])
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


## Model

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


## Workflow




## Next steps
### Incorporate next variables
- [ ] Lençol freático
- [ ] Time since burn
	- Time since last burn is very strongly correlated to number of burns, so it was removed. However, the time since each burn is probably relevant for regrowth, but I am not sure how to include this in the dataframe. For a patch that burned 5 times, or one that burned once, how do I incorporate that? should I make up to 33 columns - one with age for fire 1, other with age for fire 2, and so on?
- [ ] [L-band vegetation optical depth (_L_-_VOD_)](https://ib.remote-sensing.inrae.fr/)
- [ ] [Species density](https://www.nature.com/articles/s41467-022-32063-z)

### Data analysis
- [ ] Compare age products
	- Celso's data was 
- [ ] MAPBIOMAS classification quality - flooded forest class

 Examine disturbance of edge mature forests

- Older forests have less reliable biomass data - how can we correct for heteroskedasticity?
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


## Papers
[[Crouzeilles 2016 - Which landscape size best predicts the influence of forest cover on restoration success A global meta-analysis on the scale of effect]]