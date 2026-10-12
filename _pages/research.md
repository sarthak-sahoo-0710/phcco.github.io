---
title: Research Themes
nav_label: Research
permalink: /research/
nav: true
nav_order: 2
description: Four connected questions guide PHCCO research in computational oncology.
---

<section class="themes-intro">
  <p class="themes-lead">Cancer changes across scales: cells switch identity, tumours evolve under pressure, disease travels between organs, and every patient brings a different biological context. PHCCO connects these scales with experiments, data, and mathematical models.</p>
</section>

<div class="theme-grid">
{% for theme in site.data.research_themes %}
  <article class="theme-card" id="{{ theme.id }}">
    <img src="{{ theme.image | relative_url }}" alt="{{ theme.alt }}" loading="lazy">
    <div class="theme-card-copy">
      <p class="theme-number">Theme {{ theme.number }}</p>
      <h2>{{ theme.title }}</h2>
      <p class="theme-tagline">{{ theme.tagline }}</p>
      <p>{{ theme.description }}</p>
    </div>
  </article>
{% endfor %}
</div>

<p class="art-note">Theme artwork is an original scientific illustration created for PHCCO. It is explanatory rather than a literal microscopy image.</p>
