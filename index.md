---
layout: default
---

<!-- <h2 id="top-title">文章列表</h2> -->
<!-- <ul>
{% for post in site.posts %}
  <li class="post-{{ post.category }} post-{{ post.categories }}">
    <a href="{{ post.url }}">{{ post.title }}</a><small>{{ post.date | date_to_string }}</small>
  </li>
{% endfor %}
</ul> -->

<h2 id="top-title">帖子</h2>
{% for category in site.categories %}
  <h3>{{ category[0] }}</h3>
  <ul>
    {% for post in category[1] %}
      <li>
        <a href="{{ post.url }}">{{ post.title }}</a>
        <small>{{ post.date | date_to_string }}</small>
      </li>
    {% endfor %}
  </ul>
{% endfor %}

<!-- post >> content - excerpt - output - previous - id - url - relative_path - next - path - collection - draft - categories - layout - title - tags - date - slug - ext -->