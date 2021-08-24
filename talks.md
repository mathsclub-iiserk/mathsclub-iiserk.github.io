---
layout: default
title: Talks and Demos
permalink: /talks/
---

# Talks and Demos

This section lists all the talks and video demonstrations organized by this club.

## What is ... ?

This series of talks is aimed primarily towards 2nd and 3rd year
undergraduates. Each lecture expands upon a particular topic or object of
interest in mathematics, in a way that anyone with a basic knowledge of maths
should be able to enjoy and appreciate.

<div class="post-block">
    <ul>
        {% assign posts = site.categories.upcoming | where: "tags", "whatis" %}
        {% for post in posts %}
        {% unless post.tags contains "done" %}
            <li>
                <span class="post-date"> {{ post.futuredate | date: "%d %b %Y" }} </span>
                <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </li>
        {% endunless %}
        {% endfor %}
        
        {% assign posts = site.categories.talks | where: "tags", "whatis" %}
        {% for post in posts %}
            <li>
                <span class="post-date"> {{ post.date | date: "%d %b %Y" }} </span>
                <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </li>
        {% endfor %}
    </ul>
</div>


## Modern research

In this series, faculty members discuss present day, cutting-edge research in
their own areas, perhaps even from their current research. This is intended to
give students a flavour of what sort of problems modern mathematicians work on.

<div class="post-block">
    <ul>
        {% assign posts = site.categories.upcoming | where: "tags", "research" %}
        {% for post in posts %}
        {% unless post.tags contains "done" %}
            <li>
                <span class="post-date"> {{ post.futuredate | date: "%d %b %Y" }} </span>
                <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </li>
        {% endunless %}
        {% endfor %}
        
        {% assign posts = site.categories.talks | where: "tags", "research" %}
        {% for post in posts %}
            <li>
                <span class="post-date"> {{ post.date | date: "%d %b %Y" }} </span>
                <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </li>
        {% endfor %}
    </ul>
</div>


## Proof

This series contains short videos about a particular mathematical concept,
theorem, or even puzzles and riddles with particularly elegant solutions.

<div class="post-block">
    <ul>
        {% assign posts = site.categories.talks | where: "tags", "proof" %}
        {% for post in posts %}
            <li>
                <span class="post-date"> {{ post.date | date: "%d %b %Y" }} </span>
                <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </li>
        {% endfor %}
    </ul>
</div>
