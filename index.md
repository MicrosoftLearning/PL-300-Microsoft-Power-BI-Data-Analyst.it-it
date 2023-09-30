---
title: Istruzioni online
permalink: index.html
layout: home
---

# Directory contenuto

In basso sono elencati i collegamenti ipertestuali a tutte le demo e a tutti gli esercizi lab.

## Lab

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions'" %}
| Sezione | Lab |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}

## Demo

{% assegna demos = site.pages | where_exp:"page", "page.url contiene '/Allfiles/Demo/Instructions'" %}
| Sezione | Demo |
| --- | --- | 
{% for activity in demos  %}| {{ activity.demo.module }} | [{{ activity.demo.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
