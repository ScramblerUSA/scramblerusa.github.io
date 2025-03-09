---
layout: archive
title: "Projects"
excerpt: "A few most notable projects I'm working on..."
image:
  nofeature: lab2.png
share: true
ads: false
---

<div class="tiles">
{% for proj in site.data.projects %}
  {% include proj-grid.html %}
{% endfor %}
</div><!-- /.tiles -->
