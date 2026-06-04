---
title: Home
hide_title: true
---

# {{ site.title }}

{{ site.description }}

## Books

{% assign books = site.books | sort: "order" %}
<ul class="book-grid">
{% for book in books %}
  <li class="book-card">
    <h2><a href="{{ book.url | relative_url }}">{{ book.title }}</a></h2>
    {% if book.subtitle %}<p>{{ book.subtitle }}</p>{% endif %}
    {% if book.status == "coming-soon" %}
      <span class="status-badge">Coming soon</span>
    {% elsif book.status == "in-progress" %}
      <span class="status-badge status-badge--active">In progress</span>
    {% endif %}
    <a href="{{ book.url | relative_url }}">View book &rarr;</a>
  </li>
{% endfor %}
</ul>
