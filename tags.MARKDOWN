---
layout: base
permalink: /tags/
title: BLOG POSTS BY TAGS
---


<div class="contain-threequart">
<h1>Blog Posts by Tags</h1>
{% for tag in site.tags %}
    {% capture tag_name %}{{ tag | first }}{% endcapture %}
    <div id="#{{ tag_name | slugify }}"></div>
    <p></p>

    <h3>{{ tag_name | capitalize }}</h3>
    <a name="{{ tag_name | slugize }}"></a>
    {% for post in site.tags[tag_name] %}
    <article class="archive-item">
      <a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a>
    </article>
    {% endfor %}
{% endfor %}
</div>