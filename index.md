---
title: Istruzioni online
permalink: index.html
layout: home
---

# <a name="content-directory"></a>Directory contenuto

In basso sono elencati i collegamenti ipertestuali a tutte le demo e a tutti gli esercizi lab.

## <a name="labs"></a>Lab

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions'" %}
| Sezione | Lab |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
