---
layout: default
title: Articles
permalink: /articles/
---

# Articles

This section lists all the articles submitted to this club.

<div class="post-block">
    <ul>
        {% for post in site.categories.articles %}
            <li>
                <span class="post-date"> {{ post.date | date: "%d %b %Y" }} </span>
                <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </li>
        {% endfor %}
    </ul>
</div>
