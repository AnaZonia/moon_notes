---
up:
  - "[[Ecosystem Services]]"
stardate: Sep 16th 2023
aliases:
  - Non-Timber Forest Product (NTFP)
---

- [[Agent-Based Modelling]]
- [[Cacao Agroforestry]]
- [[What factors affect fruit production]]
- [[Nutrition from the forest]]

[Sociobioeconomia de Floresta em Pé: mais que preservação, uma solução econômica viável para desenvolvimento da Amazônia](https://theconversation.com/sociobioeconomia-de-floresta-em-pe-mais-que-preservacao-uma-solucao-economica-viavel-para-desenvolvimento-da-amazonia-220094)

[Pathways from Deforestation to Restoration | NACLA](https://nacla.org/pathways-deforestation-restoration)

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
WHERE contains(type, "article")
SORT authors ASC
```


## Who works on it

```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", at-a-glance AS "At a Glance"
FROM [[]]
WHERE contains(type, "research network") OR contains(type, "NGO") OR contains(type, "think-tank")
```
