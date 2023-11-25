---
up:
  - "[[500 Alexandria]]"
stardate: Oct 22nd 2023
update: Nov 24th 2023
---

```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", authors as "Author"
WHERE contains(type, "poetry")
SORT authors ASC
```