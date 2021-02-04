---
layout: default
title: Tags
permalink: /tags
---

# {{ page.title }}
<ul>
    {% for tag in site.tags %}
        <li>
            <a href="{{ site.baseurl }}/tags#{{ tag[0] }}">{{ tag[0] }}</a>
        </li>
    {% endfor %}
</ul>
{% for tag in site.tags %}
<h2 id="{{ tag[0] }}">{{ tag[0] }}</h2>
<ul>
    {% for post in tag[1] %}
        <li>
            {{ post.date | date: "%Y-%m-%d %H:%M:%S" }} - <a href="{{ post.url | absolute_url }}">{{ post.title }}</a>
        </li>
    {% endfor %}
</ul>
{% endfor %}