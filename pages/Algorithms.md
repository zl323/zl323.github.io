---
layout: page
title: Tags
permalink: /tags.html
# tagline: Biu~
---
<div>
  <!-- first 表示按时间顺序 tag -->
  {% capture site_tags %}{% for tag in site.tags %}{{ tag | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}
  {{site_tags}}
  {% assign tag_words = site_tags | split:',' | uniq | sort %}
  <!-- get rid of duplicate tags in the array -->
  
  <!-- 遍历所有有标签的文章并列出标题 -->
  {{tag_words}}
{% for item in tag_words %}
    {% if item == blank %} 
      {% continue %}
    {% endif %}
    {% capture this_word %}{{ item | strip_newlines }}{% endcapture %}
    <h2 id="{{ this_word | cgi_escape }}" class="tag-title">#{{ this_word }}</h2>
    <!-- lists all posts corresponding to specific tag -->
    {{site.posts.size}}
    <!-- {% for p in site.tags.this_word %} -->
      <!-- {{post.tags}} -->
    <!-- lists all posts corresponding to specific tag -->
    {% for post in site.posts %}
      {{post.tags}}
      {% if post.title != null %}
        <div class="tagged-post">
          <h3 class="title">
            <a href="{{ post.url | relative_url }}">
              {{ post.title }}
            </a>
          </h3>
          <div class="meta">
            {{ post.date | date: "%B %-d, %Y" }}
          </div>
        </div>
      {% endif %}
    {% endfor %}
    <!-- {% endfor %} -->
{% endfor %}
</div>
[返回主页](https://zl323.github.io/)