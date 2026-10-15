---
title: About
layout: custom-page
icon: fas fa-info-circle
order: 4
permalink: /about/
slug: about
description: "Background, research interests, and contact"
---

{% assign p = site.data.profile %}

<div class="about-content">
  <!-- Profile -->
  <div class="about-profile">
    <span class="about-avatar" aria-hidden="true"><i class="fas fa-user"></i></span>
    <div class="about-identity">
      <h2>{{ p.name }}</h2>
      <p class="about-identity__ko">{{ p.name_ko }}</p>
      <p class="about-identity__affiliation">
        {{ p.program }}<br>
        {{ p.institution }}
      </p>
      {% if p.status %}
      <p class="about-identity__status">{{ p.status }}</p>
      {% endif %}
    </div>
  </div>

  <!-- Research Interests -->
  <div class="about-section">
    <h3 class="section-title">My academic profile</h3>
    <div class="section-content">
      <p>My research focuses on studying the accelerated expansion of the universe. I am particularly interested how this can be understood as the inclusion of a new species called Dark Energy, that amounts to ~70% of energy budget of the universe. Alternatively, this can be thought of as a modification of our current understanding of gravity, which may behave differently on the largest scales, where the environment is particularly diffuse. To accomplish this, I am very interested in using computational and statistical tools. </p>

      <p><strong>Physics</strong></p>
      <ul>
        {% for item in p.research.physics %}
        <li>{{ item }}</li>
        {% endfor %}
      </ul>

      <p><strong>Machine Learning</strong></p>
      <ul>
        {% for item in p.research.ml %}
        <li>{{ item }}</li>
        {% endfor %}
      </ul>
    </div>
  </div>

  <!-- Publications -->
  <div class="about-section">
    <h3 class="section-title" id="publications">Publications</h3>
    <div class="section-content">
      <ul class="publication-list">
        {% for pub in p.publications %}
        <li class="publication-entry">
          <span class="publication-entry__title">
            {% if pub.url != "" %}<a href="{{ pub.url }}" target="_blank" rel="noopener">{{ pub.title }}</a>{% else %}{{ pub.title }}{% endif %}
          </span>
          <span class="publication-entry__meta">{{ pub.authors }} — {{ pub.venue }} ({{ pub.year }})</span>
        </li>
        {% endfor %}
      </ul>
    </div>
  </div>

  <!-- Contact / CV -->
  <div class="about-section">
    <h3 class="section-title">Contact</h3>
    <div class="section-content">
      <p>I am happy to recieve an emal and share any ideas and potential collaborations. Beyond my academic interests I am a music nerd, and really enjoy outdoors acitivities like hiking and cycling.</p>

      <ul class="about-links">
        {% if p.social.github %}
        <li><a href="{{ p.social.github }}" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> GitHub</a></li>
        {% endif %}
        {% if p.social.linkedin %}
        <li><a href="{{ p.social.linkedin }}" target="_blank" rel="noopener"><i class="fab fa-linkedin" aria-hidden="true"></i> LinkedIn</a></li>
        {% endif %}
        {% if p.email %}
        <li><a href="mailto:{{ p.email }}"><i class="fas fa-envelope" aria-hidden="true"></i> Email</a></li>
        {% endif %}
        {% if p.social.instagram %}
        <li><a href="{{ p.social.instagram }}" target="_blank" rel="noopener"><i class="fab fa-instagram" aria-hidden="true"></i> Instagram</a></li>
        {% endif %}
      </ul>

      {% if p.cv_url != "" %}
      <a href="{{ p.cv_url }}" class="about-cv-link" target="_blank">
        <i class="fas fa-download" aria-hidden="true"></i> Download academic CV (PDF)
      </a>
      {% endif %}
    </div>
  </div>
</div>
