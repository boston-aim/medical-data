---
layout: default
title: Categories
comments: false
---

{% assign top_categories = 'imaging::waveform::ehr' | split:'::' %}

<h1>Data Categories</h1>
{% for one_category in top_categories %}
<article role="article" class="post">
  <div id="tags {{one_category | cgi_escape}}}">
      <h2 id="{{one_category | cgi_escape}}">{{one_category | upcase}}</h2>
      {% capture this_category %}{{ one_category}}{% endcapture %}
      <ul class="posts">
        {% for post in site.categories[this_category] %}
          {% if post.title != null %}
            <li itemscope>
              <a href="{{ post.url }}">{{ post.title }}</a>
            </li>
          {% endif %}
        {% endfor %}
      </ul>
  </div>
</article>
<p></p>
{% endfor %}