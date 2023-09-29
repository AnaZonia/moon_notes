  
---
aliases: ["{{title}}"] 
year: {{date | format("YYYY")}} 
first-author: {{creators[0].lastName}}, {{creators[0].firstName}}
publisher: "{{publicationTitle}}" 
tags: {% for t in tags %} {% if t.tag not in ['Amazonia', 'Climate change', 'Biogeochemistry', 'Biodiversity'] %} #{{ t.tag }} {% endif %} {% if not loop.last %} {% endif %} {% endfor %}
url: {{url}} 
type: lit-note
at-a-glance: ""

--- 
authors: {% for t in creators %}[[{{t.lastName}}, {{t.firstName}}]]{% if not loop.last %}, {% endif %}{% endfor %}

{% for t in tags %}{% if t.tag == 'Amazonia' %}[[001 MOC Amazonia]]{% elif t.tag == 'Climate change' %}[[002 MOC Climate Change]]{% elif t.tag == 'Biogeochemistry' %}[[005 MOC Biogeochemistry]]{% elif t.tag == 'Biodiversity' %}[[Biodiversity MOC]]{% endif %}{% if not loop.last %} {% endif %}{% endfor %}

{% if bibliography %}
**Bibliography:** {{bibliography}}{% endif %} 

>[!summary] Summary
> 


{% for annotation in annotations -%} {%- if annotation.annotatedText -%} <p> {% if 'Green' in annotation.colorCategory %} <span style="color: #90EE90">{{ annotation.annotatedText }}</span> {% elif 'Red' in annotation.colorCategory %} <span style="color: #DE1738">{{ annotation.annotatedText }}</span> {% elif 'Yellow' in annotation.colorCategory %} <span style="color: #F9E076">{{ annotation.annotatedText }}</span> {% else %}<span style="color: #ADD8E6"> {{ annotation.annotatedText }}</span> {% endif %} </p>{%- endif %} {% endfor %}