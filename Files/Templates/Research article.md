  
--- 
aliases: [{{title}}] 
authors: {% for t in creators %}[[{{t.lastName}}, {{t.firstName}}]]{% if not loop.last %}, {% endif %}{% endfor %}
tags: {% for t in tags %}#{{ t.tag }}{% if not loop.last %}, {% endif %}{% endfor %}
year: {{date | format("YYYY")}} 
publisher: "{{publicationTitle}}" 
url: {{url}} 
type: [lit-note]
at-a-glance: 

--- 
{% if bibliography %}
**Bibliography:** {{bibliography}}{% endif %} 

>[!summary] Summary
> 


{% for annotation in annotations -%} {%- if annotation.annotatedText -%} <p> {% if 'Green' in annotation.colorCategory %} <span style="color: #90EE90">{{ annotation.annotatedText }}</span> {% elif 'Red' in annotation.colorCategory %} <span style="color: #DE1738">{{ annotation.annotatedText }}</span> {% elif 'Yellow' in annotation.colorCategory %} <span style="color: #F9E076">{{ annotation.annotatedText }}</span> {% else %}<span style="color: #ADD8E6"> {{ annotation.annotatedText }}</span> {% endif %} </p>{%- endif %} {% endfor %}