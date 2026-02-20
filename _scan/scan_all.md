---
layout: default
title: Scan Summary
tip: scan all
date:   2026-02-14 01:00:00 -0700
binder:
  tome:  summary  # a single word common to all levels
  level: book # book | chapter | page : presentation level of this file.
  topics: [summary]
  themes: [ ] # applies to chapter level
---

The idea here is to have a set of scripts that are able to review
various aspects of the site, potentially looking for things
like missing links or orphaned pages.

{% comment %}
## Scan (all)

[Go to Topical Pages listing]( {{ site.url | append: "/mini/mini_topical.html" }} )
{% endcomment %}

## All Scans:

{% include collection_links.html pages=site.scan %}
