  
```dataview
TABLE WITHOUT ID link(file.link, default(file.aliases[0], file.name)) AS "File", year, authors, at-a-glance FROM "2 Literature/Biogeochemistry" WHERE type = "lit-note" SORT authors ASC
```
