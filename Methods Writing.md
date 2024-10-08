---
up: "[[000 Chapter 1 - Predicting Regrowth in the Amazon]]"
stardate: Mar 26th 2024
update: Mar 26th 2024
---
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
	- predictability varies with surrounding forest cover [[Crouzeilles 2016 - Which landscape size best predicts the influence of forest cover on restoration success A global meta-analysis on the scale of effect]]
- surrounding forest biomass (mature forest cover)
	- mean forest biomass per ecoregion

### Climatic (yearly)
[[002 Data Sources#Climate|Climate Data Sources]]
- seasonality index

![](https://i.imgur.com/KkwYI56.png)

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




Everything else coming up:  
- vapor pressure deficit  
- evapotranspiration  
- seasonality  
[[Ecoregions]]

Forest plantations
### Potential correlations
- Rainfall and soil fertility (Jeff Hall)

![](https://i.imgur.com/UUaTzE8.png)

