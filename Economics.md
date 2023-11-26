---
up:
  - "[[400 Interests]]"
stardate: Nov 25th 2023
update: Nov 25th 2023
---

## Books
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", authors as "Author", tags as "Tribble?"
FROM [[]]
WHERE contains(type, "book") AND !contains(type, "textbook") AND !contains(type, "textbook")
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