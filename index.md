---
layout: default
title: "Home"
---

<section class="post-list">
  {% for post in site.posts %}
  <article class="post-item">
    {% if post.thumbnail %}
      <img class="post-thumb" src="{{ post.thumbnail | relative_url }}" alt="{{ post.title }}">
    {% else %}
      <!-- fallback thumbnail -->
      <img class="post-thumb" src="{{ '/assets/images/sample-thumb.jpg' | relative_url }}" alt="">
    {% endif %}
    <div>
      <div class="post-meta">{{ post.date | date: "%B %-d, %Y" }}{% if post.categories %} in {{ post.categories | join: ", " }}{% endif %}</div>
      <h2 class="post-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p class="excerpt">{{ post.excerpt | strip_html | truncate: 260 }}</p>
      <p><a href="{{ post.url | relative_url }}">Continue reading</a></p>
    </div>
  </article>
  {% endfor %}
</section>