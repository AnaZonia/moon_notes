## Science Officer

The Workstation is where the projects happen.
```dataview
LIST
FROM "2 Workstation"
```

[[003 Data Sources MOC]]
A map to all available data sources, remote sensing products and models

[[004 People and Networks MOC]]
A summary of relevant people, NGOs, and research networks in my field

## Learning Center

### Life Sciences
[[020 Tropical Ecology MOC]]
[[030 Biogeochemistry MOC]]
[[040 Biodiversity MOC]]

### Methods
[[060 Remote Sensing MOC]]
[[050 Statistics MOC]]

### Impacts
[[070 Eco Services and Latin America MOC]]
[[080 Climate Change MOC]]
[[100 Science Outreach MOC]]

### Other interests
Philosophy, Literature, History and Art
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

