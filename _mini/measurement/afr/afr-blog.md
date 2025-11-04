---
layout: default
title: AFR Blog
tip: AFR blog overview
date:   2025-11-04 01:00:00 -0700
binder:
  tome:  measurement  # a single word common to all levels
  level: chapter # book | chapter | blog | page : presentation level of this file.
  topics: [afr]
  themes: [ ] # applies to chapter level
  blog: measurement/afr/blog
---



## Air Fuel Ratio measurement Blog

<div>
  <ol>
  {% include binder_tome_blog_list.html collection=site.mini tome="measurement" blog="measurement/afr/blog" %}
  </ol>
</div>

---

<br>

Some old issues that should be deleted:

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


[Hardlink to the measurement collection file]( {{ site.url | append: "/mini/measurement/measurement_.html" }} )

[Hardlink to the afr blog]( {{ site.url | append: "/mini/measurement/afr/afr-blog.html" }} )

[Hardlink to a file in the afr blog directory]( {{ site.url | append: "/mini/measurement/afr/blog/afr.blog-overview.html" }} )



