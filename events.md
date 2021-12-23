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
            </li>
        {% endfor %}
    </ul>
</div>
