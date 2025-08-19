---
layout: page
title: Moments
permalink: /moments/
description:
nav: true
nav_order: 4
images:
  photoswipe: true
  spotlight: true
tabs: false
moments:
  - title: At SJTU
    dir: "/assets/img/moments/SJTU/"
    desc:
  - title: At RUC
    dir: "/assets/img/moments/RUC/"
    desc:
  - title: High School
    dir: "/assets/img/moments/high_school/"
    desc: "Memories from high school days!"
  - title: Daily
    dir: "/assets/img/moments/daily/"
    desc:
  - title: Travel
    dir: "/assets/img/moments/travel/"
    desc: "To be continued!"
  - title: Cooking
    dir: "/assets/img/moments/cooking/"
    desc: "I enjoy cooking! Even though making a successful meal isn’t always easy :)"
---

Some of my favorite moments! Loving life ❤️

<style>
.moments-masonry {
  column-count: 1;
  column-gap: 8px;
}
.moments-masonry a {
  display: block;
  break-inside: avoid;
  -webkit-column-break-inside: avoid;
  page-break-inside: avoid;
  margin-bottom: 8px;
}
.moments-masonry .tile {
  display: block;
  break-inside: avoid;
  -webkit-column-break-inside: avoid;
  page-break-inside: avoid;
  margin-bottom: 8px;
}
.moments-masonry img {
  width: 100%;
  height: auto;
  border-radius: 6px;
}
.moments-masonry video {
  width: 100%;
  height: auto;
  border-radius: 6px;
  display: block;
}
@media (min-width: 576px) {
  .moments-masonry { column-count: 2; }
}
@media (min-width: 992px) {
  .moments-masonry { column-count: 3; }
}
</style>

<div class="moments-tabs">
  <ul class="nav nav-tabs" id="momentsTabs" role="tablist">
    {% for cat in page.moments %}
    <li class="nav-item">
      <a class="nav-link {% if forloop.first %}active{% endif %}"
         id="tab-{{ cat.title | slugify }}-tab"
         data-toggle="tab"
         href="#tab-{{ cat.title | slugify }}"
         role="tab"
         aria-controls="tab-{{ cat.title | slugify }}"
         aria-selected="{% if forloop.first %}true{% else %}false{% endif %}">
        {{ cat.title }}
      </a>
    </li>
    {% endfor %}
  </ul>
  <div class="tab-content" id="momentsTabsContent" style="margin-top: 12px;">
    {% for cat in page.moments %}
    <div class="tab-pane fade {% if forloop.first %}show active{% endif %}"
         id="tab-{{ cat.title | slugify }}"
         role="tabpanel"
         aria-labelledby="tab-{{ cat.title | slugify }}-tab">
      <p>{{ cat.desc }}</p>
      {% include moments_section.liquid title=cat.title dir=cat.dir %}
    </div>
    {% endfor %}
  </div>
</div>
