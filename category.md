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

    <h2 class="category-head" style="margin-left : 0.8em">{{ category_name }}</h2> 
    <ul>
    <a name="{{ category_name | slugize }}"></a>
    {% for post in site.categories[category_name] %}
    <article class="archive-item">
      {% if post.title.size >= 80 %}
        <li type="circle"><a href="{{ site.baseurl }}{{ post.url }}">{{post.title | slice: 0, 80}}...</a></li>
      {% endif %}
      {% if post.title.size < 80 %}
         <li type="circle"><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></li>
      {% endif %}
    </article>
    {% endfor %}
    </ul>
     <br>
  </div>
{% endfor %}
</div>
