---
permalink: /
title: "ABOUT ME"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

I am **Zhen Xu**, a Master's student in Computer Science at the University of North Carolina at Chapel Hill. I am honored to be advised by Professor Tianlong Chen. My current research interests focus on:

- **Large Language Models and Mixture of Experts (MoE)**
  - Model architecture design and optimization
  - Interpretability and explainability of large language models
  
- **AI for Biological Applications**
  - Using AI methods to solve biological problems
  - AI-based prediction of biological rhythms and patterns

---

## My Academic Journey

<div class="journey-cards">
  <div class="journey-card">
    <h3>Zhejiang University</h3>
    <p class="journey-card-meta">2021 – 2025 · B.Eng, Computer Science and Technology</p>
  </div>

  <div class="journey-card">
    <h3>Peking University</h3>
    <p class="journey-card-meta">Summer 2024 · Research in Network Measurement</p>
  </div>

  <div class="journey-card">
    <h3>UNC at Chapel Hill</h3>
    <p class="journey-card-meta">2025 – Present · M.S. in Computer Science</p>
  </div>
</div>

---

## Selected Publications

{% include base_path %}

{% assign recent_pubs = site.publications | sort: 'date' | reverse | slice: 0,3 %}

{% if recent_pubs and recent_pubs.size > 0 %}
  <ul>
  {% for pub in recent_pubs %}
    <li>
      <a href="{{ pub.url | relative_url }}">{{ pub.title }}</a>
      {% if pub.venue %}
        <span> · {{ pub.venue }}</span>
      {% endif %}
      {% if pub.year %}
        <span> ({{ pub.year }})</span>
      {% endif %}
    </li>
  {% endfor %}
  </ul>
  <p><a href="{{ '/publications/' | relative_url }}">View all publications →</a></p>
{% else %}
  <p>No publications listed yet. Please check back soon.</p>
{% endif %}

