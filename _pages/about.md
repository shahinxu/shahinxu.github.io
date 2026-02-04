---
permalink: /
title: "ABOUT ME"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

I am **Zhen Xu**, a Master's student in Computer Science at the University of North Carolina at Chapel Hill, advised by Professor Tianlong Chen. I received my B.Eng in Computer Science and Technology from Zhejiang University, and spent Summer 2024 at Peking University working on network measurement research.

My work currently focuses on large language models and Mixture of Experts (MoE), including model architecture design, optimization, and understanding the interpretability and explainability of these systems. I am also interested in AI for biological applications, where I use AI methods to tackle biological problems such as predicting biological rhythms and patterns.

---

## Selected Publications

{% include base_path %}

{% assign pubs_sorted = site.publications | sort: 'date' | reverse %}
{% assign pubs_by_year = pubs_sorted | group_by_exp: 'pub', "pub.date | date: '%Y'" %}

{% if pubs_by_year and pubs_by_year.size > 0 %}
  {% for year_group in pubs_by_year %}
    <h3 class="home-pubs-year">{{ year_group.name }}</h3>
    <div class="home-pubs-list">
      {% for pub in year_group.items %}
        <div class="home-pub-item">
          {% if pub.thumbnail %}
            <div class="home-pub-thumb">
              <img src="{{ pub.thumbnail | relative_url }}" alt="{{ pub.title }} thumbnail" />
            </div>
          {% endif %}
          <div class="home-pub-content">
            <p class="home-pub-title">
              <a href="{{ pub.url | relative_url }}">{{ pub.title }}</a>
            </p>
            {% if pub.authors %}
              {% assign authors = pub.authors %}
              {% assign authors = authors | replace: 'Zhen Xu', '**Zhen Xu**' %}
              {% assign authors = authors | replace: 'Xu, Z.', '**Xu, Z.**' %}
              <p class="home-pub-authors">{{ authors | markdownify | remove: '<p>' | remove: '</p>' | strip }}</p>
            {% endif %}
            {% if pub.venue %}
              <p class="home-pub-venue">{{ pub.venue }}</p>
            {% endif %}
            {% if pub.citation %}
              <p class="home-pub-citation">{{ pub.citation }}</p>
            {% endif %}
          </div>
        </div>
      {% endfor %}
    </div>
  {% endfor %}
{% else %}
  <p>No publications listed yet. Please check back soon.</p>
{% endif %}

