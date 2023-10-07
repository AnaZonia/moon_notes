

Patterns of climate in the Amazon

Regeneration vs regrowth vs restoration 

Degredation vs deforestation vs disturbance

1. Dry vs wet tropical forests.

1. Total biomass, different growth rates. Would that be redundant with rainfall seasonality?

3. Northern Amazon is wetter, so it feels less the effect of fire. How does the model incorporate this knowledge?

## Restoration efforts

### Overview and paths to follow


[[Aliança pela Restauração da Amazônia]]

```dataview
LIST
FROM #amazonia AND !"3 Research"
WHERE !file.inlinks
SORT file.ctime DESC
```

## Amazonia Articles
```dataview
TABLE WITHOUT ID link(file.link, default(file.aliases[0], file.name)) AS "Article", year, first-author, at-a-glance FROM "3 Research" AND #amazonia SORT first_author ASC
```
