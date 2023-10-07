## Science Officer

The Workstation is where the projects happen.
```dataview
LIST
FROM "2 Workstation"
```

[[003 Data Sources MOC]]
A map to all available data sources, remote sensing products and models

[[004 People and Networks MOC]]

## Learning Center

[[020 Statistics MOC]]
[[030 Biogeochemistry MOC]]
[[040 Biodiversity MOC]]
[[050 Tropical Ecology MOC]]
[[060 Remote Sensing MOC]]
[[070 Eco Services and Latin America MOC]]
[[080 Climate Change MOC]]
[[100 Science Outreach MOC]]
[[110 Interests MOC]]


## The Warp Core
What keeps the ship running
[[120 R Data Visualization MOC]]

[[130 Python MOC]]

[[140 Notetaking MOC]]

[[150 Writing Science MOC]]

[[160 Literature Review MOC]]

Also, guides to [[Github]] and [[Obsidian Menu]].

## Books
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", file.tags AS "Tags"
WHERE contains(type, "book")
SORT file.name ASC
```

## Talks
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", file.tags AS "Tags"
WHERE contains(type, "talk")
SORT file.name ASC
```

## Tribbles

```dataview
TABLE file.cday AS "stardate"  
FROM #tribble and -"Templates"
SORT file.cday ASC
```

