---
up: "[[001 The Bridge]]"
stardate: Aug 18th 2023
update: Nov 24th 2023
dg-publish: true
---

[[Data Analysis]]
[[Model]]


## Main Points
### Scale
Previous models have done things using plots or aggregated data (medians). This will make predictions at broad scales but is not predictive at small scales which are relevant for management

### Context specificity
The regrowth potential changes with a combination of environmental predictors, 

### Satellite data limitations
There is a delay between real regrowth moment and the identified regrowth by the current algorithms (Mapbiomas and EU TMF). This has real consequences for land use management since reforestation is primarily important in early regrowth. So far, the only trends identifiable from remote sensing from space are for forests between approximately 30-65 years old.


compare differences in intercepts with differnt age data


bulk density and N

- Look into the predicted distribution of parameter values
- Look into the past with high-resolution and 
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

Remake this plot for EU data


### Make final product
- [ ] Compare results with previous models
	- Show if there are fundamental differences between what the predictions would have been vs what they are now
		- get the key areas
		- absolute values (differences)
- [ ] Determine active vs. passive reforestation
	- Given the importance of surrounding forest cover, I should be able to determine how distance to mature forest can determine whether active or passive reforestation is recommended
- [ ] Make a confidence metric map
