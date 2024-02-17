---
title: Esercitazioni di Microsoft Learn - Nozioni fondamentali sull'intelligenza artificiale di Azure
permalink: index.html
layout: home
---

# Esercizi per Concetti fondamentali su Azure per intelligenza artificiale

Questi esercizi pratici sono progettati a supporto del contenuto per la formazione in [Microsoft Learn](https://docs.microsoft.com/training/).

Per completare gli esercizi, sarà necessaria una sottoscrizione di Microsoft Azure. È possibile iscriversi per una versione di prova gratuita all'indirizzo [https://azure.microsoft.com](https://azure.microsoft.com).

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions'" %}
| Esercizi |
| ------- | 
{% for activity in labs  %}| [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}