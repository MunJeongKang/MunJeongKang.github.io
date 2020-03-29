---
layout: page
title: category
permalink: /category.html
ref: category
order: 2
---

------
<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div id="#{{ category_name | slugize }}"></div>
    <p></p>
    <center><h2 class="category-head">{{ category_name }}</h2> </center>
    <a name="{{ category_name | slugize }}"></a>
    {% for post in site.categories[category_name] %}
    <article class="archive-item">
      {% if post.title.size >= 80 %}
        <center> <a href="{{ site.baseurl }}{{ post.url }}">{{post.title | slice: 0, 80}}...</a></center>
      {% endif %}
      {% if post.title.size < 80 %}
         <center><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></center>
      {% endif %}
    </article>
    {% endfor %}
     <br>
  </div>
{% endfor %}
</div>
