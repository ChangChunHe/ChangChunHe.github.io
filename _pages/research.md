---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
header:
  og_image: "research/ecdf.png"
---

我的主要研究内容是基于第一性原理计算的数据，建立合理的物理模型对已有的理论或实验现象进行解释，并预测可能的高性能材料。

<nbsp>

{% include base_path %}

{% assign ordered_pages = site.research | sort:"order_number" %}

{% for post in ordered_pages %}
  {% include archive-single.html type="grid" %}
{% endfor %}
