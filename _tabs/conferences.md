---
title: Conferences
layout: custom-page
icon: fas fa-camera
order: 2
permalink: /conferences/
slug: conferences
description: "Photos and memories from academic conferences, workshops, and seasonal schools."
---

{% assign conf = site.data.conferences %}

<div class="conferences-container">
  <!-- Category Filter Buttons -->
  <div class="conferences-filter" role="tablist" aria-label="Event categories">
    {% for cat in conf.categories %}
    <button
      type="button"
      class="filter-btn{% if forloop.first %} active{% endif %}"
      data-filter="{{ cat.id }}"
      role="tab"
      aria-selected="{% if forloop.first %}true{% else %}false{% endif %}"
    >
      {{ cat.name }}
    </button>
    {% endfor %}
  </div>

  <!-- Events & Photo Galleries -->
  <div class="events-list">
    {% for event in conf.events %}
    <article class="event-card" data-category="{{ event.category }}">
      <div class="event-header">
        <div class="event-title-group">
          <h2 class="event-title">{{ event.title }}</h2>
          <div class="event-meta">
            <span><i class="fas fa-map-marker-alt" aria-hidden="true"></i>{{ event.location }}</span>
            <span><i class="far fa-calendar" aria-hidden="true"></i>{{ event.year }}</span>
          </div>
        </div>
        <span class="event-badge">{{ event.type }}</span>
      </div>

      {% if event.description %}
      <p class="event-description">{{ event.description }}</p>
      {% endif %}

      {% if event.photos and event.photos.size > 0 %}
      <div class="photo-grid">
        {% for photo in event.photos %}
        <figure class="photo-card">
          <img src="{{ photo.src | relative_url }}" alt="{{ photo.caption | default: event.title }}" loading="lazy">
          {% if photo.caption %}
          <figcaption class="photo-caption">{{ photo.caption }}</figcaption>
          {% endif %}
        </figure>
        {% endfor %}
      </div>
      {% else %}
      <div class="photo-placeholder">
        <i class="fas fa-camera" aria-hidden="true"></i>
        <span>Photos coming soon. Drop images into <code>assets/img/conferences/</code> and list them in <code>_data/conferences.yml</code>.</span>
      </div>
      {% endif %}
    </article>
    {% endfor %}
  </div>
</div>

<script>
  (function () {
    var buttons = Array.from(document.querySelectorAll('.filter-btn'));
    var cards = Array.from(document.querySelectorAll('.event-card'));

    buttons.forEach(function (btn) {
      btn.addEventListener('click', function () {
        var filter = btn.getAttribute('data-filter');

        buttons.forEach(function (b) {
          var active = b === btn;
          b.classList.toggle('active', active);
          b.setAttribute('aria-selected', active);
        });

        cards.forEach(function (card) {
          if (filter === 'all' || card.getAttribute('data-category') === filter) {
            card.style.display = 'flex';
          } else {
            card.style.display = 'none';
          }
        });
      });
    });
  })();
</script>
