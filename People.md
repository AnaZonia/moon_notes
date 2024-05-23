 
```dataview
TABLE WITHOUT ID link(file.link, file.name) as Person, location as Location, up as Topic
WHERE contains(type, "researcher")
SORT location
```
