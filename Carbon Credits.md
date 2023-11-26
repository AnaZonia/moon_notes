---
up:
  - "[[Climate Change]]"
  - "[[Economics]]"
stardate: Nov 25th 2023
update: Nov 25th 2023
---

## Reports
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", authors as "Author", tags as "Tribble?"
FROM [[]]
WHERE contains(type, "report")
SORT authors ASC
```
## Articles
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", authors as "Author", tags as "Tribble?"
FROM [[]]
WHERE contains(type, "article") AND !contains(type, "scicomm_article")
SORT authors ASC
```

## Resources
- [Rainforest carbon credit schemes misleading and ineffective, finds report | Carbon offsetting | The Guardian](https://www.theguardian.com/environment/2023/sep/15/rainforest-carbon-credit-schemes-misleading-and-ineffective-finds-report?CMP=share_btn_tw)
- [Artigo de opinião](https://www.migalhas.com.br/depeso/317537/credito-de-carbono--dinheiro-verde) de Hélio Gurgel, advogado ambientalista em Recife.