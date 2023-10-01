  
---
aliases: ["{{title}}"] 
year: {{date | format("YYYY")}} 
first-author: {{creators[0].lastName}}, {{creators[0].firstName}}
publisher: "{{publicationTitle}}" 
tags: {% for t in tags %} {% if t.tag not in ['Amazonia', 'Climate change', 'Biogeochemistry', 'Biodiversity'] %} #{{ t.tag }} {% endif %} {% if not loop.last %} {% endif %} {% endfor %}
url: {{url}} 
type: lit_note
at-a-glance: ""

--- 

>[!summary] Summary
> 

{% if bibliography %}**Bibliography:** {{bibliography}}{% endif %} 
{% for t in tags %}{% if t.tag == 'amazonia' %}[[010 Amazonia MOC]]{% elif t.tag == 'climate_change' %}[[020 Climate Change MOC]]{% elif t.tag == 'biogeochemistry' %}[[050 Biogeochemistry MOC]]{% elif t.tag == 'biodiversity' %}[[070 Biodiversity MOC]]{% endif %}{% if not loop.last %} {% endif %}{% endfor %}
#### Authors:
{% for t in creators %}[[{{t.lastName}}, {{t.firstName}}]]{% if not loop.last %}, {% endif %}{% endfor %}
#### Notes:
{% for annotation in annotations -%} {%- if annotation.annotatedText -%} <p> {% if 'Green' in annotation.colorCategory %} <span style="color: #90EE90">{{ annotation.annotatedText }}</span> {% elif 'Red' in annotation.colorCategory %} <span style="color: #DE1738">{{ annotation.annotatedText }}</span> {% elif 'Yellow' in annotation.colorCategory %} <span style="color: #F9E076">{{ annotation.annotatedText }}</span> {% else %}<span style="color: #ADD8E6"> {{ annotation.annotatedText }}</span> {% endif %} </p>{%- endif %} {% endfor %}