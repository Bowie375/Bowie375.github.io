---
permalink: /
title: "Bowen Xiao (肖博文)"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<p>I'm an graduate student at <a href="https://www.pku.edu.cn">Peking University</a>, majoring in Computer Science.</p>
<p>My current research interests are in the field of deformable object manipulation and tactile sensing.</p>

<h1>News</h1>
<ul>
  <li>[2026.01]: <a href = "https://arxiv.org/abs/2505.09109">FoldNet</a> is accepted by RAL 2026.</li>
  <li>[2025.07]: <a href = "https://arxiv.org/abs/2412.01083">Robohanger</a> is accepted by RAL 2025.</li>
</ul>

<h1>Publications</h1>
{% for post in site.publications reversed %}
  {% include archive-single-publication.html %}
{% endfor %}

<h1>Services</h1>
<ul>
  <li>[2026.03 - 2026.06]: Teaching assistant for undergraduate course <a href = "https://pku-epic.github.io/Intro2CV_2026/">Introduction to Computer Vision</a>.</li>
</ul>
