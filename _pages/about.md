---
permalink: /
title: "Bowen Xiao (肖博文)"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<p>I'm an 3rd year undergraduate student at <a href="https://www.pku.edu.cn">Peking University</a>, majoring in Computer Science.</p>
<p>My research interests are in the field of deformable object manipulation.</p>

<h1>News</h1>
<ul>
  <li>[2025.07]: <a href = "https://arxiv.org/abs/2412.01083">Robohanger</a> is accepted by RAL 2025.</li>
</ul>

<h1>Publications</h1>
{% for post in site.publications reversed %}
  {% include archive-single-publication.html %}
{% endfor %}

<h1>Services</h1>