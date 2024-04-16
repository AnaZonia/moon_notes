---
up: 
stardate: Oct 2nd 2023
update: Nov 24th 2023
dg-publish: true
---

## Research Networks
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", at-a-glance, up 
WHERE contains(type, "research network")
SORT file.ctime DESC
```

## NGOs
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", at-a-glance, up
WHERE contains(type, "NGO")
SORT file.ctime DESC
```

## Think tanks
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", at-a-glance, up
WHERE contains(type, "think-tank")
SORT file.ctime DESC
```

## Activism and Policy
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", at-a-glance, up
WHERE contains(type, "policy")
SORT file.ctime DESC
```

## Outreach Groups
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Name", location
WHERE contains(type, "outreach_group")
SORT location DESC
```


## Researchers
![[People]]
