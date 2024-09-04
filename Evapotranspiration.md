---
up:
  - "[[Biogeochemistry]]"
  - "[[ECOSTRESS]]"
stardate: Oct 9th 2023
update: Oct 9th 2023
---
> [!glossary]  Total water loss from soil to the atmosphere through evaporation and transpiration.

## Potential Evapotranspiration (PET)
- The maximum amount of water that a system can transpire, given water saturation. *Hotter temperatures increase this value*, so it is not constant for an area across time.
- Arid climates always have PET > precipitation.
- **Can be obtained from remote sensing in three ways:**
	- extrapolating point measured values to whole landscape based on vegetation indices
	- use thermal infrared to obtain ET from surface energy balance (SEB)
	- Penman-Monteith physical model

### Penman-Monteith
Described in [Allen et al 1998](https://www.fao.org/3/X0490E/X0490E00.htm)

![](https://i.imgur.com/xGC2Hqq.png)

Inputs:
- Radiation
- Soil heat flux
- Air temperature and humidity to calculate [[Vapor Pressure Deficit]]
- Windspeed and surface rouchness to estimate aerodynamic and surface resistances.

Also explained well in:
[Ekstrom et al 2007](https://hal.science/hal-00305649/)

![](https://i.imgur.com/QGWVBzV.png)

Psychrometric constant for tropical forests

And on [[MODIS]] [ATBC](https://lpdaac.usgs.gov/documents/93/MOD16_ATBD.pdf), which works to overcome the grass reference constraint with LAI and Land cover information:

![](https://i.imgur.com/zT4AlgS.png)


## Actual Evapotranspiration (AET)
- How much water is actually transpired.
- In [[TerraClimate]] it is calculated as *precipitation plus soil water utilized*, through a climatic water-balance model.
- On [Allen et al 1998](https://www.fao.org/3/X0490E/x0490e0a.htm#chapter%205%20%20%20introduction%20to%20crop%20evapotranspiration%20(etc))it is calculated as a crop constant K_c x PET.
### Thornthwaite-Mather climatic water balance model (WBM)