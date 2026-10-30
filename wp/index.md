---
layout: default
title: My_WP
permalink: /wp/
---

{% comment %}
  My_WP 总览页：/wp/
  - 分类清单来自 _data/wp.yml，新增比赛不用改这里
  - 文章只要 front matter 里有 categories: [WP, "某比赛名"]，就会出现在下面的列表
{% endcomment %}

# My_WP

这里按比赛分类整理我写的所有 WP（Writeup）文章。

## 比赛分类

<ul class="category-list">
  {% for cat in site.data.wp.categories %}
    {% assign cat_posts = site.categories[cat.name] %}
    <li>
      <a class="post-link" href="{{ '/wp/' | append: cat.slug | append: '/' | relative_url }}">{{ cat.name }}</a>
      <span class="post-count">（{{ cat_posts | size }} 篇）</span>
    </li>
  {% endfor %}
</ul>

## 全部 WP 文章

<ul class="post-list">
  {% assign wp_posts = site.categories['WP'] %}
  {% for post in wp_posts %}
    <li>
      <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
      <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      {% comment %}除 WP 之外的分类名做成小标签显示{% endcomment %}
      {% for c in post.categories %}{% unless c == 'WP' %}<span class="post-category">{{ c }}</span>{% endunless %}{% endfor %}
      <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 100 }}</p>
    </li>
  {% else %}
    <li>暂无 WP 文章，敬请期待。</li>
  {% endfor %}
</ul>
