---
up:
  - "[[Forest Dynamics]]"
stardate: Oct 7th 2023
update: Oct 7th 2023
aliases:
  - Regeneration
  - Restoration
---

- [[Is active reforestation more efficient than passive]]
- [[The effect of animals on regrowth]]
- [[Costa Rican regrowth context]]
- [[Modelling Regrowth]]
- [[What is the current contribution of forest regrowth to carbon sequestration]]


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
