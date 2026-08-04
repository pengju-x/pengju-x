---
layout: default
title: "博客"
lang: zh
permalink: /blog/
pagination:
  enabled: true
  collection: posts
  per_page: 10
  permalink: '/page/:num/'
  title_suffix: ' - 第 :num 页'
---

<h1>📝 全部博客</h1>

<ul class="post-list">
  {% for post in paginator.posts %}
    <li>
      <span class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</span>
      <h2>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h2>
      <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
    </li>
  {% endfor %}
</ul>

<!-- 分页导航 -->
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path | relative_url }}" class="prev">« 上一页</a>
  {% endif %}

  <span class="page-number">第 {{ paginator.page }} 页 / 共 {{ paginator.total_pages }} 页</span>

  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path | relative_url }}" class="next">下一页 »</a>
  {% endif %}
</div>