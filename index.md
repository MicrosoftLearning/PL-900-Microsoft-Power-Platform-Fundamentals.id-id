---
title: Petunjuk Host Online
permalink: index.html
layout: home
---

# Direktori Konten

Hyperlink ke masing-masing latihan dan demo lab tercantum di bawah ini.

## Lab

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %}
| Modul | Laboratorium |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}

## Demo

{% assign demos = site.pages | where_exp:"page", "page.url berisi '/Instructions/Demos'" %}
| Modul | Demo |
| --- | --- | 
{% for activity in demos  %}| {{ activity.demo.module }} | [{{ activity.demo.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
