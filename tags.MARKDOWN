---
layout: base
permalink: /tags/
title: BLOG POSTS BY TAGS
---

<div class="container">
<div class="contain-threequart">
<h1>Blog Posts by Tags</h1>
<h3>Tag List</h3>
{% for tag in site.tags  %}
      {% assign tag_name = tag[0] %}
      {% assign taglist = taglist | append: tag_name |append: "@" %}
    {% endfor %}
    {% assign sorted_taglist = taglist | split: "@" |sort %}
    {% for sorted_tag in sorted_taglist %}
    <a href="#{{ sorted_tag | slugify }}" class="box-link-brown">{{ sorted_tag }}</a>
{% endfor %}

{% for sorted_tag in sorted_taglist %}
	<div id="{{ sorted_tag | slugify }}" style="padding-top:10px;"></div>
    <h3>{{ sorted_tag | capitalize }}</h3>
    <ul>
    {% for post in site.posts %}
      {% if post.tags contains sorted_tag %}
      <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}
      </a> ⋅ <span class="post-meta">{{ post.date | date_to_string }}</span> </li> 
      {% endif %}
    {% endfor %}
    </ul>
{% endfor %}
</div>
</div>