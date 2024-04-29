---
up: 
stardate: Sep 29th 2023
update: Apr 3rd 2024
dg-publish: true
---
## Land Use and Land Cover
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", mission AS "Mission", time_range AS "Time Range", type as "Type"
WHERE contains(type, "land_cover") OR contains(type, "forest_change")
SORT type ASC
```

## Forest Plots
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", time_range AS "Time Range"
WHERE contains(type, "plots")
SORT file.name ASC
```


## Plant Traits
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", type as "Type"
WHERE contains(type, "plant_traits") OR contains(type, "nitrogen_fixers") OR contains(type, "wood_density")
SORT type ASC
```

## Biomass
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", mission AS "Mission", time_range AS "Time Range", type as "Type"
WHERE contains(type, "biomass") OR contains(type, "canopy_height")
SORT type ASC
```

## Fire
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", mission AS "Mission", time_range AS "Time Range", type as "Type"
WHERE contains(type, "active_fire") OR contains(type, "burned_area")
SORT type ASC
```

## Climate

```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", time_range AS "Time Range", type as "Type"
WHERE contains(type, "climate")
SORT type ASC
```

## Soil
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", mission AS "Mission", time_range AS "Time Range"
WHERE contains(type, "soil")
SORT file.name ASC
```


## Other Data Repositories:
- [Serviço Nacional de Informações Florestais (SNIF)](https://snif.florestal.gov.br/pt-br/)
- [Global Forest Watch](https://www.globalforestwatch.org)  
- [SINIA (Sistema Nacional de Información Ambiental) - Panama](https://www.sinia.gob.pa/index.php/cobertura-boscosa/ano-2019/a-nivel-nacional)
- [FAO Forest Inventory](https://microdata.fao.org/index.php/catalog/Forestry/?page=1&sort_by=popularity&sort_order=desc&ps=15&repo=Forestry)
- [[SiBBr - Sistema de Informação sobre a Biodiversidade Brasileira]]
- [SUS -AlertaDengue](https://github.com/AlertaDengue/PySUS)
