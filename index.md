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
    <a href="{{ post.url }}">{{ post.title }}</a><abbr>{{ post.date | date_to_string }}</abbr>
  {% endif %}
  </li>
{% endfor %}
</ul>

---

<h2 id="top-title">分类</h2>
<ul>
{% for category in site.categories %}
  {% for post in site.categories[category] %}
    <li class="">
      <a href="{{ post.url }}">{{ post.title }}</a><abbr>{{ post.date | date_to_string }}</abbr>
    </li>
    
  {% endfor %}
{% endfor %}
</ul>