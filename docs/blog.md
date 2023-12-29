---
layout: page
permalink: /blog/
title: Blog
usemathjax: true
---
Here are my blog posts. I will occasionally write about theorems or lemmas
that I come across which are particularly neat or elegant. I originally 
intended to write mostly about Euclidean geometry techniques, but as you can
see I failed to do that a long time ago.

<div>
    {%- if site.posts.size > 0 -%}
        <ul class="post-list">
        {%- for post in site.posts -%}
        <li>
            {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
            <span class="post-meta">{{ post.date | date: date_format }}</span>
            <h3>
            <a class="post-link" href="{{ post.url | relative_url }}">
                {{ post.title | escape }}
            </a>
            </h3>
            {%- if site.show_excerpts -%}
            {{ post.excerpt }}
            {%- endif -%}
        </li>
        {%- endfor -%}
        </ul>
    {%- endif -%}
</div>