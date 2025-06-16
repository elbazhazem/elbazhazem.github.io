---
layout: default
title: "Blogs"
---

I'm documenting my learning and reflections as I transition from traditional cybersecurity into the world of AI. These posts include technical insights, lessons learned, and personal perspectives.

{% if site.show_excerpts %}
  {% include home.html %}
{% else %}
  {% include archive.html title="Posts" %}
{% endif %}
