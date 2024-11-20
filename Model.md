---
up:
  - "[[000 Chapter 1 - Predicting Regrowth in Brazil]]"
stardate: Nov 17th 2024
update: Nov 17th 2024
dg-publish: true
---
## Introducing flexibility into k
- splines
- genetic algorithms
- neural networks
- hybrid models (XGBoost?)
- Mutual information  
- Late fusion

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