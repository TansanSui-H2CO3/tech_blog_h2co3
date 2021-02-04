---
layout: default
title: Archives
permalink: /archives
---
# {{ page.title }}
<ul>
    {% for post in site.posts %}
        <li>
            {{ post.date | date: "%Y-%m-%d %H:%M:%S" }} - <a href="{{ post.url | absolute_url }}">{{ post.title }}</a>
        </li>
    {% endfor %}
</ul>