---
layout: default
---

<div>
  {% for post in site.posts %}
    <small>{{ post.date | date: "%-d %B %Y" }}</small>
    <h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
    {{ post.excerpt }}
    <hr />
  {% endfor %}
</div>
