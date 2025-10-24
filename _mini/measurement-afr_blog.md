---
layout: default
title: Notebook
date:   2025-10-22 01:00:00 -0700
binder:
  tome:  measurement  # a single word common to all levels in the work 
  level: chapter # identifies presentation level of this file.
  topics: [ ] # applies to book level
  themes: [ AFR ] # applies to chapter level
---

Ideally an AFR notebook blog list appears here...

{% comment %}
Posts:

{% for post in site.posts %}
  <h4> {{ post.date }} {{ post.title }} </h4>
{% endfor %}
{% endcomment %}

{% comment %}
Mini site all files:

{% for file in site.mini %}
  <h4> {{ file.date }} {{ file.title }} </h4>
{% endfor %}
{% endcomment %}

{% comment %}
MiniUrl:

{% for item in site.mini %}
  <h4> {{ item.url }} </h4>
{% endfor %}
{% endcomment %}

{% comment %}
blog:

{% for file in site.mini.blog %}
  <h4> {{ file.date }} {{ file.title }} </h4>
{% endfor %}

blog/afr:

{% for file in site.mini.blog.afr %}
  <h4> {{ file }} </h4>
  <h4> {{ file.date }} {{ file.title }} </h4>
{% endfor %}

raw site.mini.blog

{{ site.mini.blog }}

raw site.mini

{{ site.mini }}
{% endcomment %}


[Hardlink to a collection file]( {{ site.url | append: "/mini/history_.html" }} )

[Hardlink to a file in the root blog directory]( {{ site.url | append: "/mini/blog/blog_.html" }} )

[Hardlink to a file in the afr blog directory]( {{ site.url | append: "/mini/blog/afr/afr_.html" }} )

The *measurement/afr* blog:
<div>
  <ol>
  {% include binder_tome_blog_list.html collection=site.mini tome="measurement" blog="measurement/afr" %}
  </ol>
</div>
