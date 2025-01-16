---
layout: home
permalink: /
title: "Home page"
share: true
---

Welcome to my projects page!

I created this site to share my big and little projects, add-ons to other projects and random ideas with the world.
One of the reasons is difficulty of contributing to community projects due to heavy gatekeeping or owner unavailabilty. Sometimes your pull request just sits there for months with no feedback at all. Then it gets lost to time. Other times maintainers would enforce some arbitrary rules, making you redo your work over and over again. It gets frustrating really quickly. Don't get me wrong, I would understand scrutiny in some core component, but will never understand it for plugins, add-ons, user mods, etc.
So I decided to share my creations through my own git repositories and document them on this site.

Here's the glimpse of what's going on:

<div class="tiles">
{% for post in site.posts limit:8 %}
	{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->

(see the [articles](/articles) page for complete list)


<footer class="page-footer">
{% if page.share != false %}{% include share-this.html %}{% endif %}
{% include page-meta.html %}
</footer><!-- /.footer -->

