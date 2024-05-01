---
up: "[[001 The Bridge]]"
stardate: Aug 18th 2023
update: Nov 24th 2023
dg-publish: true
---

### Writing
- [[Background Writing]]
- [[Background Flowchart.canvas|Background Flowchart]]
- [[Methods Writing]]
- [[Methods Flowchart - Predicting Regrowth in the Amazon.canvas|Methods Flowchart]]

## Methods

### Land use
- number of years under fallow
- time since last fire
- total number of fires
- total years under each land use type
- last observed land use type

### Landscape
- soil type ([[FAO Soil Map of the World]] or [[Zuquim 2023 - Introducing a map of soil base cation concentration, an ecologically relevant GIS-layer for Amazonian forests]])
- protected areas
- indigenous areas
- ecoregions
- fragmentation ([[Ma 2023 - Global forest fragmentation change from 2000 to 2020]])

### Climatic (yearly)
[[002 Data Sources#Climate|Climate Data Sources]]
- seasonality index
- mean annual precipitation
- [[Evapotranspiration]]
- [[Vapor Pressure]]
- [[Latent Heat Flux]]
- [[Cumulative Water Deficit]]
- [[Leaf Area Index]]

### Model

#### Incorporating climate history
$$
\mathrm{AGB}=B_0+A_{\max }(1-\underbrace{e^{-k} \cdot e^{-k} \cdots \cdot e^{-k} \cdot e^{-k}}_{t \text { times }})^\tau
$$
$$
\mathrm{AGB}=B_0+A_{\max }\left(1-\left(e^{-k_1} \cdot e^{-k_2} \cdot \cdots \cdot e^{-k_{t-1}} \cdot e^{-k_t}\right)\right)^T=
$$

$$
\mathrm{AGB}=B_0+A_{\max }\left(1-e^{-k t}\right)^\tau
$$
$$ AGB = B_{max}(1-\prod_{t=1}^{t_\text{max}}e^{- (E_t+LU)})
$$

#### Land use and landscape predictors
$$

AGB = B_{max}(1-e^{-\sum_{t=1}^{t_\text{max}} (E_t+LU)})

$$
$$
E = \beta_{P} P + \beta_{T} T + \beta_{S_t} S_T + \beta_{S_p} S_P + \beta_{S_i}
$$
$$
LU = \beta_{F} F * e^{\beta_{F_\tau} \tau_{f}}
+ \beta_{\text{LU}_1} LU_1 * e^{\beta_{\text{LU1}_\tau} \tau_{1}}
+ \beta_{\text{LU}_2} LU_2 * e^{\beta_{\text{LU2}_\tau} \tau_{2}}
 + ... 
+ \beta_{\text{LU}_n} LU_n * e^{\beta_{\text{LUn}_\tau} \tau_{n}}
$$

#### Log-transform
Linearize the model

### Optimizers
- Hamiltonian Monte Carlo
	- Can be hard to use discrete values of parameters. Values from HMC can be input into optim
	- [PyStan](https://pystan.readthedocs.io/en/latest/)
- MCMC
- [Generalized differential evolution](https://ieeexplore.ieee.org/document/8167916)
- [Simulated Annealing](https://machinelearningmastery.com/simulated-annealing-from-scratch-in-python/)
	- [optim_sa](https://search.r-project.org/CRAN/refmans/optimization/html/optim_sa.html)
	- [anneal](https://search.r-project.org/CRAN/refmans/likelihood/html/anneal.html)
	- [from scratch](https://jmsallan.netlify.app/blog/coding-simulated-annealing-in-r/)

## Questions
### Error is related to biomass
- Older forests have less reliable biomass data - no way around it. What does that mean for us?

### Correlated variables
- Dry areas burn more often
- Pastureland may also be burned more frequently

### Distribution of errors
The standard deviation tending towards the upper end may mean the errors are not normally distributed. Checking the distribution of errors would help.

### Older forests have less history to learn from than young forests
- Restrict to only the last 5 years before regrowth. That would miss 
- Run it only for forests up to 15 years old
- Mask off to include only what was mature in 1985
1. Total biomass, different growth rates. Would that be redundant with rainfall seasonality?

### MAPBIOMAS classification confidence per forest class

- [ ] look into flooded forest class
