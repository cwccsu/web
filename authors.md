---
layout: page
title: Authors
comments: false
permalink: /authors/
---

<div id="authors">
{% for person in site.data.people %}
<h3 id="{{ username }}">{{ person[1].name }}</h3>
<ul class="posts">
{% for post in site.posts %}
{% if person[1].username == post.author %}
{% if post.title != null %}
<li itemscope><span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">{{ post.date | date: "%B %d, %Y" }}</time></span> &raquo; <a href="{{ site.baseurl }}{{ post.url | remove: '/'}}">{{ post.title }}</a></li>
{% endif %}
{% endif %}
{% endfor %}
</ul>
<hr>
{% endfor %}
</div>
