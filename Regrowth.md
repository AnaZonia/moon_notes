---
up:
  - "[[Tropical Forest Ecology]]"
stardate: Apr 23rd 2024
update: Apr 23rd 2024
dg-publish: true
---
[[Regrowth.canvas|Regrowth Flowchart]]

- [[Forest Restoration]]
- [[Regrowth on Landslides]]


## People
```dataview
TABLE WITHOUT ID link(file.link, file.name) as "Name", location
FROM [[]]
WHERE contains(type, "researcher")
```

## Papers
```dataview
LIST
FROM "2 Research"
WHERE contains(file.outlinks, this.file.link)
SORT file.name ASC
```
