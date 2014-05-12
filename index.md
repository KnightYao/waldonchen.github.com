---
layout: page
title: 我的文章
tagline:
---
{% include JB/setup %}


{% for post in site.posts %}
  {% capture this_year %}{{ post.date | date: "%Y" }}{% endcapture %}
  {% capture this_month %}{{ post.date | date: "%B" }}{% endcapture %}
  {% capture next_year %}{{ post.previous.date | date: "%Y" }}{% endcapture %}
  {% capture next_month %}{{ post.previous.date | date: "%B" }}{% endcapture %}

 {% if forloop.first %}
<h2>{{ this_year }}</h2>
<ul>
  {% endif %}

<li><a href="{{ BASE_PATH }}{{post.url}}">{{ post.title }}</a></li>

  {% if forloop.last %}
</ul>
  {% else %}
    {% if this_year != next_year %}
</ul>
<h2>{{ next_year }}</h2>
<ul>
    {% else %}
{% comment %}
    {% if this_month != next_month %}
</ul>
<h3>{{ next_month }}</h3>
<ul>
      {% endif %}
{% endcomment %}
    {% endif %}
  {% endif %}
{% endfor %}

<!-- {% for post in posts_collate %} -->
  <!-- {% capture this_year %}{{ post.date | date: "%Y" }}{% endcapture %} -->
  <!-- {% capture this_month %}{{ post.date | date: "%B" }}{% endcapture %} -->
  <!-- {% capture next_year %}{{ post.previous.date | date: "%Y" }}{% endcapture %} -->
  <!-- {% capture next_month %}{{ post.previous.date | date: "%B" }}{% endcapture %} -->

  <!-- {% if forloop.first %} -->
  <!-- <h2>{{this_year}}</h2> -->
  <!-- <h2>{{this_month}}</h2> -->
  <!-- <ul> -->
  <!-- {% endif %} -->

  <!-- <li><span>{{ post.date | date: "%B %e, %Y" }}</span> &raquo; <a href="{{ BASE_PATH }}{{post.url}}">{{ post.title }}</a></li> -->

  <!-- {% if forloop.last %} -->
  <!-- </ul> -->
  <!-- {% else %} -->
    <!-- {% if this_year != next_year %} -->
      <!-- </ul> -->
      <!-- <h2>{{next_year}}</h2> -->
      <!-- <h3>{{next_month}}</h3> -->
      <!-- <ul> -->
    <!-- {% else %} -->
      <!-- {% if this_month != next_month %} -->
        <!-- </ul> -->
        <!-- <h3>{{next_month}}</h3> -->
        <!-- <ul> -->
      <!-- {% endif %} -->
    <!-- {% endif %} -->
  <!-- {% endif %} -->
<!-- {% endfor %} -->
<!-- {% assign posts_collate = nil %} -->
