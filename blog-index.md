---
layout: default
permalink: /blog/
---

<div class="posts">
  {% for post in site.posts %}
    <article class="post">
      <h3><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h3>
      <div class="datetime">
        كُتب في {{ post.date | date: "%d/%m/%Y" }}
      </div>
    </article>
  {% endfor %}
</div>
