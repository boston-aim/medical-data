---
layout: default
title: Tags
---

<h1>All tags</h1>

<article role="article" class="post">
{% assign tags = site.tags | sort %}
<ul>
    {% for tag in tags %}
    <li>
        <a href="/tag/{{ tag | first | slugify }}/">{{ tag[0] | replace:'-', ' ' }} ({{ tag | last | size }})</a>
    </li>

    {% endfor %}
</ul>
</article>