---
layout: default
title: Events
permalink: /events/
---

# Events

This section lists all events organized by the club.

<div class="post-block">
    <ul>
        {% for post in site.categories.events %}
            <li>
                <span class="post-date"> {{ post.date | date: "%d %b %Y" }} </span>
                <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
                {% if post.author %}
                    <span class="dot">•</span>
                    <span class="post-author">{{ post.author }}</span>
                {% endif %}
                {% if post.blurb %}
                    <div class="post-blurb">{{ post.blurb | markdownify }}</div>
                {% endif %}
            </li>
        {% endfor %}
    </ul>
</div>
