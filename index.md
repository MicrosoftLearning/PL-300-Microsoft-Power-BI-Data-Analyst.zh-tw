---
title: 線上託管說明
permalink: index.html
layout: home
---

# 內容目錄

下方列出可連至各實驗室活動和示範的超連結。

> **注意**：如果您遇到內容的任何錯誤，請[在 GitHub 儲存庫](https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/issues/new/choose)中建立新問題。

## 實驗室練習

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %}
| 模組 | 實驗室 |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}

## 示範

{% assign demos = site.pages | where_exp:"page", "page.url contains '/Instructions/Demos'" %}

| 示範 |
| --- |
{% for activity in demos  %}| [{{ activity.demo.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
