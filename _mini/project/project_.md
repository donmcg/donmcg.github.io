---
layout: default
title: Mini Projects (book)
tip: mini project overview
date:   2025-10-30 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels
  level: book # book | chapter | page : presentation level of this file.
  topics: [project]
  themes: [ ] # applies to chapter level
---

So many projects...

### Chapter themes:
<ol>
{% include binder_tome_chapter_themes_list.html collection=site.mini tome="project" %}
</ol>

### Book topics:
<ol>
{% include binder_tome_book_topics_list.html collection=site.mini tome="project" %}
</ol>
{% comment %}
{% endcomment %}
