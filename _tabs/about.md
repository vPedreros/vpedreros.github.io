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
    {% if p.avatar %}
    <img class="about-avatar" src="{{ p.avatar | relative_url }}" alt="{{ p.name }}">
    {% else %}
    <span class="about-avatar" aria-hidden="true"><i class="fas fa-user"></i></span>
    {% endif %}
    <div class="about-identity">
      <h2>{{ p.name }}</h2>
      {% if p.name_ko %}
      <p class="about-identity__ko">{{ p.name_ko }}</p>
      {% endif %}
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
      <p>My research focuses on studying the accelerated expansion of the universe. I am particularly interested how this can be understood as the inclusion of a new species called Dark Energy, that amounts to ~70% of energy budget of the universe. Alternatively, this can be thought of as a modification of our current understanding of gravity, which may behave differently on the largest scales, where the environment is particularly diffuse. To accomplish this, I am very interested in using computational and statistical tools.</p>

      {% if p.research.physics and p.research.physics.size > 0 %}
      <p><strong>Physics</strong></p>
      <ul>
        {% for item in p.research.physics %}
        <li>{{ item }}</li>
        {% endfor %}
      </ul>
      {% endif %}

      {% if p.research.ml and p.research.ml.size > 0 %}
      <p><strong>Machine Learning</strong></p>
      <ul>
        {% for item in p.research.ml %}
        <li>{{ item }}</li>
        {% endfor %}
      </ul>
      {% endif %}
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
            {% if pub.url and pub.url != "" and pub.url != "In prep." and pub.url contains "://" %}
              <a href="{{ pub.url }}" target="_blank" rel="noopener">{{ pub.title }}</a>
            {% else %}
              {{ pub.title }}
            {% endif %}
          </span>
          <span class="publication-entry__meta">{{ pub.authors }} — {{ pub.venue }} ({{ pub.year }}){% if pub.url == "In prep." %} · <em>In prep.</em>{% endif %}</span>
        </li>
        {% endfor %}
      </ul>
    </div>
  </div>

  <!-- Contact / CV -->
  <div class="about-section">
    <h3 class="section-title">Contact</h3>
    <div class="section-content">
      <p>I am happy to receive an email and share any ideas and potential collaborations. Beyond my academic interests I am a music nerd, and really enjoy outdoor activities like hiking and cycling.</p>

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
        {% if p.social.lastfm or p.social.last_fm or p.social['last.fm'] %}
        <li><a href="{{ p.social.lastfm | default: p.social.last_fm | default: p.social['last.fm'] }}" target="_blank" rel="noopener"><i class="fab fa-lastfm" aria-hidden="true"></i> Last.fm</a></li>
        {% endif %}
        {% if p.social.instagram %}
        <li><a href="{{ p.social.instagram }}" target="_blank" rel="noopener"><i class="fab fa-instagram" aria-hidden="true"></i> Instagram</a></li>
        {% endif %}
      </ul>

      {% if p.cv_url and p.cv_url != "" %}
      <a href="{{ p.cv_url }}" class="about-cv-link" target="_blank">
        <i class="fas fa-download" aria-hidden="true"></i> Download academic CV (PDF)
      </a>
      {% endif %}
    </div>
  </div>
</div>
