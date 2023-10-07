---
title: 線上託管說明
permalink: index.html
layout: home
---

# 內容目錄

下方列出可連至各實驗室活動和示範的超連結。

## 實驗室

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions'" %}
| 區段 | 實驗室 |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}

<!---
## Demos

{% assign demos = site.pages | where_exp:"page", "page.url contains '/Instructions/Demos'" %}
| Section | Demo |
| --- | --- | 
{% for activity in demos  %}| {{ activity.demo.module }} | [{{ activity.demo.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
---> 
