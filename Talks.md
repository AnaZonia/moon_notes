```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", up as "Parent"
WHERE contains(type, "talk")
SORT file.name ASC
```