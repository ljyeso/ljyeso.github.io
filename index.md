---
layout: default
---

<h2 id="top-title">文章列表</h2>
<ul>
{% for post in site.posts %}
  <li class="post-{{ post.category }}">
  {% if post.external_url %}
    <a href="{{ post.url }}">{{ post.title }}</a><abbr>{{ post.date | date_to_string }}</abbr>
  {% else %}
    <a href="{{ post.external_url }}">{{ post.external_url }}{{ post.title }}{{ post.url }}</a><abbr>{{ post.date | date_to_string }}</abbr>
  {% endif %}
  </li>
{% endfor %}
</ul>
