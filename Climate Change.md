---
up:
  - "[[200 Life Sciences]]"
stardate: Sep 12th 2023
update: Nov 9th 2023
---

- [[Carbon Tax]]
- [[Carbon Credits]]
- [[Carbon Exports]]
- [[Títulos Verdes]]
- [[Debt-for-climate swaps]]
- [[Green New Deal]]
- [[Non-CO2 Greenhouse gases]]
- [[What is the current contribution of forest regrowth to carbon sequestration]]
[[Evidence and attribution of the land carbon sink's historic enhancement]]


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

## Who works on it

```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", at-a-glance AS "At a Glance"
FROM [[]]
WHERE contains(type, "research network") OR contains(type, "NGO") OR contains(type, "think-tank") OR contains(type, "policy")
```



