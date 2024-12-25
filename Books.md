---
up:
  - "[[Alexandria]]"
stardate: Oct 22nd 2023
update: Nov 24th 2023
dg-publish: true
---


```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", authors as "Author", up AS "Topic"
WHERE contains(type, "book") AND !contains(type, "textbook")
SORT authors ASC
```