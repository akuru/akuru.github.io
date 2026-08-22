---
layout: default
title: Projects
permalink: /projects/
---
{% assign t = site.data.i18n[site.lang] %}
<section class="wrap">
  <div class="section-head" style="margin-top:3rem;">
    <h2>{{ t.projects_heading }}</h2>
  </div>
  {% assign projects = site.projects | sort: 'order' %}
  <div class="grid">
    {% for p in projects %}
    <a class="card" href="{{ p.url | relative_url }}">
      {% if p.cover %}
      <div class="thumb"><img src="{{ p.image_base | append: p.cover | relative_url }}" alt="{{ p.title }}" loading="lazy"></div>
      {% else %}
      <div class="thumb empty">අ</div>
      {% endif %}
      <h3>{{ p.title }}</h3>
      {% if p.meta %}<div class="meta">{{ p.meta }}</div>{% endif %}
    </a>
    {% endfor %}
  </div>
</section>
