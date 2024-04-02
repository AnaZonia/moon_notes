---
up:
  - "[[Biogeochemistry]]"
stardate: Nov 28th 2023
update: Nov 28th 2023
---

Can be calculated in multiple different ways.

1. [[Chave 2014]]
Similar to what was done by Malhi and Aragão, but does a total sum rather than reaching for the minimum value, so magnitudes change.

Evapotranspiration is obtained from [[Climate Research Unit (CRU)]] rather than considered 100 for the whole Amazon. This could be an issue as the CRU ET value is derived from a Penman-Monteith equation with grass-based parameters.

2. [[TerraClimate]]
CWD = ET_0 - AET
**Caveat**: Evapotranspiration is calculated with grass as a reference - useless in the Amazon!
CWD is *positive* here - 

3. Malhi et al 2009 and Aragão et al 2007
Calculation used on [[Heinrich 2021 - Large carbon sink potential of secondary forests in the Brazilian Amazon to mitigate climate change]] with [[TerraClimate]] rainfall.
ET is fixed at 100mm/month.
Most negative CWD obtained over a year, with monthly change being precipitation - evapotranspiration. What was last month's deficit + how much rained this month - how much we lost to ET this month.
CWD = 0 when the soil is saturated with water.
ET is fixed at 100mm/month. (total)

![](https://i.imgur.com/o4lVmM7.png)


- I don't think I will have measures of ET going back to 1985 - MODIS only goes back to 2000. I may be stuck with the fixed measure of ET.


