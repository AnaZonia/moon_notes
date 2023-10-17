## Science Officer
The Workstation is where the projects happen.
```dataview
LIST
FROM "2 Workstation"
```
[[003 Data Sources]]
Summary of data on LULC, forest plots, plant traits, biomass, fire, climate and soil

[[004 First Contact]]
Summary of relevant people, NGOs, and research networks

- Preservação e recuperação da floresta
	1. Ecologia de paisagem
		- Dinâmica florestal (como uma comunidade muda com o amadurecimento de uma floresta? o que limita o crescimento?)
		- Biodiversidade
		- Contexto ecológico latinoamericano-brasileiro (cerrado, florestas montanhosas, caatinga, mata atlântica, amazônia, pantanal)
	1. Biogeoquímica & Botânica
		- Ciclo de nutrientes (nitrogênio e fósforo principalmente)
		- Fisiologia vegetal
			- Fotossíntese
			- Fixação de nitrogênio
			- Reprodução (produção de frutos e flores)
	2. Serviços ecossistêmicos e políticas de conservação
		- Como planejar a restauração de ecossistemas mantendo em mente o bem-estar das populações rurais? Onde há uma interseção da saúde da floresta (recuperação de biodiversidade e biomassa) e saúde humana?
			- Produtos florestais não-madeireiros
			- Agrofloresta
		- Como estabelecer uma comunicação eficiente entre os meios acadêmico e político, pra informar decisões com mais eficiência?
			- Política ambiental
			- Legislação ambiental
			- Comunicação científica
- Previsões confiáveis de dinâmica florestal
	1. Estatística
		- Estatística frequentista - qual correlação há entre certos fatores, e qual a nossa incerteza?
			- Regressão, modelos aditivos, modelos mistos, verossimilhança máxima, etc
		- Estatística bayesiana - como o conhecimento prévio afeta as nossas conclusões futuras?
			- Redes bayesianas, otimização
		- Aprendizado de máquina - como usar computadores pra executar algoritmos baseados em métodos estatísticos?
			- RandomForest
			- Neural Networks
				- Deep Learning
			- Decision Trees
			- Naive Bayes
			- K-means clustering
	2. Sensoriamento Remoto
		1. Produtos
			- Multi-hiper spectral
				- Classificação de uso de terra
			- Radar
			- LiDAR
	 3. Ferramentas
		- QGIS
		- GDAL
		- Python
		- R
		- Google Earth Engine

### Quantitative
- [[110 Remote Sensing]]
- [[120 Statistics]]
- [[130 Python]]
- [[140 R programming]]

### Life Sciences
- [[210 Tropical Ecology]]
- [[220 Biogeochemistry]]
- [[230 Biodiversity]]
- [[240 Theoretical Ecology]]

### Conservation
- [[310 Latin American Agriculture]]
- [[320 Climate Change]]

### Other interests
- [[410 Interests]]

### Communication
- [[510 Notetaking]]
- [[520 Writing Science]]
- [[530 Literature Review]]
- [[540 Debates and Discourse]]
- [[550 Science Outreach]]

## Books
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", up AS "Parent"
WHERE contains(type, "book")
SORT file.name ASC
```

## Talks
```dataview
TABLE WITHOUT ID link(file.link, file.name) AS "Title", up as "Parent"
WHERE contains(type, "talk")
SORT file.name ASC
```

## Tribbles

```dataview
TABLE file.cday AS "stardate"  
FROM #tribble and -"Templates"
SORT file.cday ASC
```


