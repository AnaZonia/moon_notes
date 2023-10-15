## Science Officer
The Workstation is where the projects happen.
```dataview
LIST
FROM "2 Workstation"
```
[[003 Data Sources]]
Summary of data on LULC, forest plots, plant traits, biomass, fire, climate and soil

[[004 First Contact]]
Summary of relevant people, NGOs, and research networks

### Quantitative
- [[110 Remote Sensing]]
- [[120 Statistics]]
- [[130 Python]]
- [[140 R programming]]

### Life Sciences
- [[210 Tropical Ecology]]
- [[220 Biogeochemistry]]
- [[230 Biodiversity]]
- [[240 Theoretical Ecology]]

### Conservation
- [[310 Latin American Agriculture]]
- [[320 Climate Change]]

### Other interests
- [[410 Interests]]

### Communication
- [[510 Notetaking]]
- [[520 Writing Science]]
- [[530 Literature Review]]
- [[540 Debates and Discourse]]
- [[550 Science Outreach]]

## Books
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", up AS "Parent"
WHERE contains(type, "book")
SORT file.name ASC
```

## Talks
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", up as "Parent"
WHERE contains(type, "talk")
SORT file.name ASC
```

## Tribbles

```dataview
TABLE file.cday AS "stardate"  
FROM #tribble and -"Templates"
SORT file.cday ASC
```


