---
layout: page
title: ""
subtitle: "Data Science, Machine Learning, Python"
# date: 2022-04-25 06:07:13
background: "/img/DataScience.jpg"
Categories: "DataScience"
permalink: /DataScience/
---

### Data Science blog posts page

<!-- Post List -->
{% for post in site.posts limit : 5 %}
{% if post.categories contains "DataScience" %}
<article class="post-preview">
    <a href="{{ post.url | prepend: site.baseurl | replace: '//', '/' }}">
    <h2 class="post-title">{{ post.title }}</h2>
    {% if post.subtitle %}
    <h3 class="post-subtitle">{{ post.subtitle }}</h3>
    {% else %}
    <h3 class="post-subtitle">{{ post.excerpt | strip_html | truncatewords: 15 }}</h3>
    {% endif %}
    </a>
    <p class="post-meta">
    {{ post.date | date: '%B %d, %Y' }} &middot; {% include read_time.html content=post.content %}
    </p>
</article>

<hr>

{% endif %}
{% endfor %}
