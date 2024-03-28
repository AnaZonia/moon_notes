---
up:
  - "[[200 Life Sciences]]"
stardate: Sep 12th 2023
update: Nov 9th 2023
---

## Policy and Economics
- [[Carbon Tax]]
- [[Carbon Credits]]
- [[Carbon Exports]]
- [[Títulos Verdes]]
- [[Debt-for-climate swaps]]
- [[Green New Deal]]
- [[Incentives to Forest Growth.canvas|Incentives to Forest Growth - NEO]]
- [[Canadian Contributions to Climate Change - Pollution and Mining]]

## Science
- [[Non-CO2 Greenhouse gases]]
- [[ENSO - El Niño-Southern Oscillation]]



## Books
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", authors as "Author", tags as "Tribble?"
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

## Who works on it

```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", at-a-glance AS "At a Glance"
FROM [[]]
WHERE contains(type, "research network") OR contains(type, "NGO") OR contains(type, "think-tank") OR contains(type, "policy")
```



