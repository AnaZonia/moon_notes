
## Research Networks
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", at-a-glance 
FROM "7 People and Networks"
WHERE contains(type, "research network")
SORT file.ctime DESC
```

## NGOs
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", at-a-glance 
FROM "7 People and Networks"
WHERE contains(type, "NGO")
SORT file.ctime DESC
```

## Think tanks
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", at-a-glance 
FROM "7 People and Networks"
WHERE contains(type, "think-tank")
SORT file.ctime DESC
```

## Activists and Policymakers
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", at-a-glance 
FROM "7 People and Networks"
WHERE contains(type, "activist")
SORT file.ctime DESC
```

## Researchers
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", at-a-glance 
FROM "7 People and Networks"
WHERE contains(type, "researcher")
SORT file.ctime DESC
```
