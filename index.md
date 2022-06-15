---
title: Istruzioni online
permalink: index.html
layout: home
ms.openlocfilehash: 0c2c63aea8926ec06e02203a9ff9a9a5d5cc9b85
ms.sourcegitcommit: 9f66e4932aaf188d3be327646561dc7fe8e5c7a5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2022
ms.locfileid: "143996840"
---
# <a name="content-directory"></a>Directory contenuto

In basso sono elencati i collegamenti ipertestuali a tutte le demo e a tutti gli esercizi lab.

## <a name="labs"></a>Lab

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions'" %}
| Modulo | Lab |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
