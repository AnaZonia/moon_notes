---
up:
  - "[[200 Life Sciences]]"
stardate: Sep 30th 2023
update: Sep 30th 2023
---

- [[Why do the tropics have higher biodiversity]]
- [[Biodiversity - Biomass Relationship]]
- [[Biodiversity exchange in the tropics]]
- [[How is biodiversity loss happening]]
- [[Niche Theory]]


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

## Papers
```dataview
LIST
FROM "2 Research"
WHERE contains(file.outlinks, this.file.link)
SORT file.name ASC
```