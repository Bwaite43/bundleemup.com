---
layout: page
title: Browse by town
description: "Updates grouped by tag."
permalink: /tags.html
---

{% capture site_tags %}{% for tag in site.tags %}{{ tag | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}
{% assign tags_list = site_tags | split:',' | sort %}

<ul class="tag-list">
  {% for this_word in tags_list %}
  <li><a class="tag" href="#{{ this_word | slugify }}">{{ this_word }} ({{ site.tags[this_word].size }})</a></li>
  {% endfor %}
</ul>

{% for this_word in tags_list %}
<h3 id="{{ this_word | slugify }}">{{ this_word }}</h3>
<ul>
  {% for post in site.tags[this_word] %}{% if post.title != null %}
  <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
  {% endif %}{% endfor %}
</ul>
{% endfor %}
