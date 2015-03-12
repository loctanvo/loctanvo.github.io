---
layout: post
title: Loc Tan Vo | Blog
permalink: /blog/
---


<h1 class="page-heading">Posts</h1>
<div>
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt | truncatewords:30 }}
    </li>
  {% endfor %}
</ul>

  <p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.baseurl }}">via RSS</a></p>
</div>


  
