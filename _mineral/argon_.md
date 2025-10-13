---
date:   2025-10-12 01:00:00 -0700
title: Argon book
binder:
  tome:  argon  # a single word common to all levels in the tome 
  level: book # identifies presentation level of this file.
  topics: [ noble ] # applies to book level
  themes: [ theme1, theme2 ] # applies to chapter level

book: argon
level: book
topics: [noble]
reference:
  level: book
  book: argon
  chapter: 
  page:

family: nonmetal
group: gas
---
file argon_.md

Argon appears as few compounds.

Here are the book chapters for argon:
<ol>
{% comment %}
{% include book_chapter_list.html pages=site.mineral files=site.mineral book="argon" %}
{% endcomment %}
{% include binder_tome_chapter_themes_list.html collection=site.mineral tome="argon" %}
</ol>

