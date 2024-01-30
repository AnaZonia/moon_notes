---
up:
  - "[[400 Interests]]"
stardate: Nov 25th 2023
update: Nov 25th 2023
---
- [[Historical Ecology]]
- [[Latin American History]]
- [[European History]]
- [[Iranian History]]
[World History Encyclopedia](https://www.worldhistory.org/)


## Books
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", authors as "Author"
FROM [[]]
WHERE contains(type, "book") AND !contains(type, "textbook")
SORT authors ASC
```