---
up:
  - "[[Alexandria]]"
stardate: Oct 22nd 2023
update: Nov 24th 2023
---

```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", authors as "Author", up AS "Topic"
WHERE contains(type, "textbook")
SORT authors, up ASC
```