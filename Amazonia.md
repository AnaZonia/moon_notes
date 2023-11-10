---
up:
  - "[[Tropical Ecology]]"
stardate: Aug 22nd 2023
update: Oct 7th 2023
tags: []
---
Patterns of climate in the Amazon
Peatlands/turfeiras
Regeneration vs regrowth vs restoration 

Degredation vs deforestation vs disturbance

1. Dry vs wet tropical forests.

1. Total biomass, different growth rates. Would that be redundant with rainfall seasonality?

3. Northern Amazon is wetter, so it feels less the effect of fire. How does the model incorporate this knowledge?

[[Water Stress]] in the Amazonian context:
- The east and southeastern parts of the forest actually go months each year with little or no rain. The trees survive by tapping soil moisture as far down as 20 meters.

## Restoration efforts

### Overview and paths to follow


[[Aliança pela Restauração da Amazônia]]

```dataview
LIST
FROM #amazonia
WHERE !file.inlinks
SORT file.ctime DESC
```
**The changing carbon balance in Amazonia**  **+ discussion  
**Paulo Artaxo - Instituto de Física da Universidade de Sao Paulo
[Max Planck Jena seminar Amazonia Short 4 May 2022.pdf - MPI for Biogeochemistry (mpg.de)](https://nextcloud.bgc-jena.mpg.de/s/nZez8tmK7Ng99Xa?dir=undefined&openfile=38259529)


## Amazonia Articles
```dataview
TABLE WITHOUT ID link(file.link, default(file.aliases[0], file.name)) AS "Article", year, first-author, at-a-glance FROM "3 Research" AND #amazonia SORT first_author ASC
```
[Functional traits and niche-based tree community assembly in an Amazonian forest - PubMed (nih.gov)](https://pubmed.ncbi.nlm.nih.gov/18948539/)