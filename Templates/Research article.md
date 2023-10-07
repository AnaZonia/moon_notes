  
---
aliases: ["{{title}}"] 
year: {{date | format("YYYY")}} 
first-author: {{creators[0].lastName}}, {{creators[0].firstName}}
publisher: "{{publicationTitle}}" 
tags: [{% for t in tags %}{{ t.tag }}, {% if not loop.last %}{% endif %}{% endfor %}]
url: {{url}} 
type: lit_note
at-a-glance: ""

--- 
#tribble
>[!summary] Summary

>[!quote] Cited

#### Authors:
{% for t in creators %}[[{{t.lastName}}, {{t.firstName}}]]{% if not loop.last %}, {% endif %}{% endfor %}
#### Notes:
{% for annotation in annotations -%} {%- if annotation.annotatedText -%} {% if 'Green' in annotation.colorCategory %} 
> <span style="color: #90EE90">{{ annotation.annotatedText }}</span> 

{% elif 'Red' in annotation.colorCategory %} 

> <span style="color: #FFC0CB">{{ annotation.annotatedText }}</span>

{% elif 'Yellow' in annotation.colorCategory %}

 > <span style="color: #F9E076">{{ annotation.annotatedText }}</span>

{% else %} 
 > <span style="color: #ADD8E6"> {{ annotation.annotatedText }}</span> 

{% endif %}{%- endif %} {% endfor %}