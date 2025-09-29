---
layout: default
title: Blog
---

{% comment %}
# about this web site
- bullet one
{% include navigation.html %}
{% endcomment %}

# All posts
**Starting at most recent...**

{% for post in site.posts %}
1.   [{{ post.title }}]( {{ post.url }} )
{% endfor %}

{% comment %}
1.   {{ post.date }} [{{ post.title }}]( {{ post.url }} )
######  {{ post.excerpt }}
    <li>
      <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
<!--			{{ post.excerpt }} -->
<!--      {{ post.content }} -->
    </li>
{% endcomment %}
