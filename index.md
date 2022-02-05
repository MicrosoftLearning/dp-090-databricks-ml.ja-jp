---
title: オンライン ホステッド インストラクション
permalink: index.html
layout: home
---

# コンテンツ ディレクトリ

ラボの演習は以下のとおりです。

## ラボ

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %}
| モジュール | ラボ |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
