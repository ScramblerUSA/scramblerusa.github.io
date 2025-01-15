---
layout: archive
title: "SimpleDiySmartHome"
tags: []
image:
  feature: sdsh_feature.jpg
---

This is a work in progress.

<div class="tiles">
{% for post in site.categories.sdsh %}
	{% assign proj_teaser = 'sdsh_teaser.png' %}
	{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->
