
## Research Networks
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", at-a-glance, up 
FROM "6 First Contact"
WHERE contains(type, "research network")
SORT file.ctime DESC
```

## NGOs
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", at-a-glance, up
FROM "6 First Contact"
WHERE contains(type, "NGO")
SORT file.ctime DESC
```

## Think tanks
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", at-a-glance, up
FROM "6 First Contact"
WHERE contains(type, "think-tank")
SORT file.ctime DESC
```

## Activism and Policy
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", at-a-glance, up
FROM "6 First Contact"
WHERE contains(type, "policy")
SORT file.ctime DESC
```

## Researchers
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", up
FROM "6 First Contact"
WHERE contains(type, "researcher")
SORT up DESC
```


## Outreach Group
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", location
FROM "6 First Contact"
WHERE contains(type, "outreach_group")
SORT location DESC
```