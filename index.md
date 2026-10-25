---
layout: default
title: 首页
---

# 欢迎来到我的博客

这里记录我的脑洞hhh...

## 最新文章

<ul class="post-list">
  {% for post in site.posts limit:5 %}
    <li>
      <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
      <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 100 }}</p>
    </li>
  {% endfor %}
</ul>

<p class="all-posts-link"><a href="{{ '/blog/' | relative_url }}">查看全部文章 &rarr;</a></p>
