  
---
aliases: ["{{title}}"] 
year: {{date | format("YYYY")}} 
first-author: {{creators[0].lastName}}, {{creators[0].firstName}}
publisher: "{{publicationTitle}}" 
tags:[{% for t in tags %}{% if t.tag in ['review', 'meta_analysis', 'number_one', 'model', 'synthesis', 'thesis', 'data/plots'] %}{{ t.tag }}, {% endif %}{% if not loop.last %}{% endif %}{% endfor %}]
url: {{url}} 
type: lit_note
at-a-glance: ""

--- 

{% for t in tags %}{% if t.tag not in ['review', 'meta_analysis', 'number_one', 'model', 'synthesis', 'thesis', 'data/plots'] %}[[{{t.tag}}]]{% endif %}{% if not loop.last %} {% endif %}{% endfor %}

>[!quote] Cited
#### Authors:
{% for t in creators %}[[{{t.lastName}}, {{t.firstName}}]]{% if not loop.last %}, {% endif %}{% endfor %}

#### Notes:
{% set seen_texts = [] %}
{% for annotation in annotations -%}
  {%- if annotation.annotatedText and annotation.annotatedText not in seen_texts -%}
    {% set seen_texts = seen_texts + [annotation.annotatedText] %}
    {% if 'Green' in annotation.colorCategory %}
> <span style="color: #90EE90">{{ annotation.annotatedText }}</span>
    {% elif 'Yellow' in annotation.colorCategory %}
> <span style="color: #F9E076">{{ annotation.annotatedText }}</span>
    {% endif %}
  {%- endif %}
{% endfor %}
