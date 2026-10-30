---
layout: default
title: "_萌新"
permalink: /wp/mengxin/
---

{% comment %}
  单个比赛的 WP 列表页模板：
  - 新增比赛时，复制本文件为 wp/新slug.md
  - 改 3 处：title（显示名）、permalink（/wp/新slug/）、下面的 site.categories['比赛名']
  - 并在 _data/wp.yml 里加一项，菜单才会出现
{% endcomment %}

# _萌新

<p class="back-link"><a href="{{ '/wp/' | relative_url }}">&larr; 返回 My_WP</a></p>

<ul class="post-list">
  {% assign cat_posts = site.categories['_萌新'] %}
  {% for post in cat_posts %}
    <li>
      <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
      <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 100 }}</p>
    </li>
  {% else %}
    <li>暂无文章，敬请期待。</li>
  {% endfor %}
</ul>
