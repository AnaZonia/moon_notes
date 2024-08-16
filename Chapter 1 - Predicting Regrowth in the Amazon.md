---
up: "[[001 The Bridge]]"
stardate: Aug 18th 2023
update: Nov 24th 2023
dg-publish: true
---
## Writing
- [[Background Flowchart.canvas|Background Flowchart]]
- [[Methods Writing]]
- [[Methods Flowchart - Predicting Regrowth in the Amazon.canvas|Methods Flowchart]]
APA reference, 2 column, lato

## Working on

- Check what is going on with google earth engine
- Finish STAN
- Finish RAY

- Finish mature forest kriging

[[Gatti - Amazonia as Carbon Source]]
[[Leung - Clustered vs catastrophic declines]]

## Optimizers
### Hamiltonian Monte Carlo

- Can be hard to use discrete values of parameters. Values from HMC can be input into optim
	- [PyStan](https://pystan.readthedocs.io/en/latest/)
	- STAN

[How to use Bayesian Inference for predictions in Python | by Pedro Martins de Bastos | Towards Data Science](https://towardsdatascience.com/how-to-use-bayesian-inference-for-predictions-in-python-4de5d0bc84f3)

### Hyperparameter tuning
 
 [src/ax_client_qNEHVI_pwe.py · master · hosseinjafar / WeightOptimizationGPUCB · GitLab](https://gitlab.com/hosseinjafar/weightoptimizationgpucb/-/blob/master/src/ax_client_qNEHVI_pwe.py?ref_type=heads)
- Can be used with Monte Carlo

### Evolution-based algorithms
- [Generalized differential evolution](https://ieeexplore.ieee.org/document/8167916)
- [Simulated Annealing](https://machinelearningmastery.com/simulated-annealing-from-scratch-in-python/)
	- [optim_sa](https://search.r-project.org/CRAN/refmans/optimization/html/optim_sa.html)
	- [anneal](https://search.r-project.org/CRAN/refmans/likelihood/html/anneal.html)
	- [from scratch](https://jmsallan.netlify.app/blog/coding-simulated-annealing-in-r/)


## Questions
### Error is related to biomass
- Older forests have less reliable biomass data - how can we correct for heteroskedasticity?

### Correlated variables
- Dry areas burn more often
- Pastureland may also be burned more frequently
- How can I analyse correlations?

### Distribution of errors
The standard deviation tending towards the upper end may mean the errors are not normally distributed. Checking the distribution of errors would help.

### Older forests have less history to learn from than young forests
- Restrict to only the last 5 years before regrowth. That would miss 
- Run it only for forests up to 15 years old
- Mask off to include only what was mature in 1985
1. Total biomass, different growth rates. Would that be redundant with rainfall seasonality?

### Time since burn
Still unsure how to include this in the dataframe, since there are different amounts of burn events - for a patch that burned 5 times, or one that burned once, how do I incorporate that? should I make up to 33 columns - one with age for fire 1, other with age for fire 2, and so on?

### Other things to look into
- [ ] MAPBIOMAS classification quality - flooded forest class
- [ ] Lençol freático
- [ ] differentiating mature forests and fallow (everything that is mature from 1985 onwards)

<!--⚠️Imgur upload failed, check dev console-->
![[Chapter 1 - Predicting Regrowth in the Amazon.png]]