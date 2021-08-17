---
layout: default
title: Monthly Contests
permalink: /contests/
---

# Monthly Contests

This is an archive of all monthly contests organized by the club. Every month,
an interesting problem is posted; solutions are received over a period of 3
weeks. The best solutions are awarded and shared by the end of the month.

<div class="post-block">
    <ul>
        {% for post in site.categories.contests %}
            <li>
                <span class="post-date"> {{ post.date | date: "%d %b %Y" }} </span>
                <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </li>
        {% endfor %}
    </ul>
</div>
