---
layout: default
title: "菜鸟杯"
permalink: /wp/cainiaobei/
---

{% comment %}
  单个比赛的 WP 列表页模板（做法同 mengxin.md）：
  - title / permalink / site.categories['比赛名'] 三处要和 _data/wp.yml 保持一致
{% endcomment %}

# 菜鸟杯

<p class="back-link"><a href="{{ '/wp/' | relative_url }}">&larr; 返回 My_WP</a></p>

<ul class="post-list">
  {% assign cat_posts = site.categories['菜鸟杯'] %}
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
