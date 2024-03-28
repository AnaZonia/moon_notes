---
up:
  - "[[Tropical Forest Ecology]]"
stardate: Aug 22nd 2023
update: Oct 7th 2023
tags: 
dg-publish: true
---
### Amazonian Landscape
- [[Climate Patterns in the Amazon]]
- [[Peatlands]]
- [[White Sand]]
- [[Tipos de Mata na Amazônia]]
- [[Fogo na Amazonia]]
- [[História da Amazônia]]
- [[Amazonian Indigenous Peoples]]
- [[The Tipping Point]]
- [[The Changing Carbon Balance in Amazonia]]

### Quotable facts on the Amazon
- It's the size of the continental US
- 1/5 of the world's freshwater runs through it
- Over 50% of the remaining rainforests in the world
- It absorbs one fourth of the CO2 absorbed by all land on Earth, but that's 30% less now than in the 1990s due to deforestation.
- Brazil's CO2 emissions have dropped more than any other country over the past 20 years - there is improvement.

## Books
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", authors as "Author"
FROM [[]]
WHERE contains(type, "book") AND !contains(type, "textbook")
SORT authors ASC
```

## Reports
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", authors as "Author", tags as "Tribble?"
FROM [[]]
WHERE contains(type, "report")
SORT authors ASC
```

## Articles
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", authors as "Author", tags as "Tribble?"
FROM [[]]
WHERE contains(type, "article") AND !contains(type, "scicomm_article")
SORT authors ASC
```

## Talks
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", authors as "Author", tags as "Tribble?"
FROM [[]]
WHERE contains(type, "talk")
SORT authors ASC
```

## Networks

```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", at-a-glance AS "At a Glance"
FROM [[]]
WHERE contains(type, "research network") OR contains(type, "NGO") OR contains(type, "think-tank") OR contains(type, "policy")
```



## People
```dataview
TABLE WITHOUT ID link(file.link, file.name), location
FROM [[]]
WHERE contains(type, "researcher")
```