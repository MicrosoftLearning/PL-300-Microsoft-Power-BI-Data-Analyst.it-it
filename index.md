---
title: Istruzioni ospitate online
permalink: index.html
layout: home
---

# Directory contenuto

In basso sono elencati i collegamenti ipertestuali a tutti gli esercizi e alle demo del lab.

## Esercitazioni

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %}
| Corso | Modulo | Lab |
| --- |--- | --- | 
{% for activity in labs  %}| {{ activity.lab.course }} |{{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}

## Demo

{% assign demos = site.pages | where_exp:"page", "page.url contains '/Instructions/Demos'" %}
| Corso | Modulo | Demo |
| --- |--- | --- | 
{% for activity in demos  %}| {{ activity.demo.course }} |{{ activity.demo.module }} | [{{ activity.demo.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
