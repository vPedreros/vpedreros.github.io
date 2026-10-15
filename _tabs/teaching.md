---
title: Teaching
layout: custom-page
icon: fas fa-chalkboard-teacher
order: 2
permalink: /teaching/
slug: teaching
description: "Course materials, auxiliary lecture guides, evaluations, and teaching archives from Universidad de Chile."
---

{% assign t = site.data.teaching %}

<div class="about-content">
  <div class="about-section">
    <h3 class="section-title">Teaching Experience</h3>
    <div class="section-content">
      <p>
        As a former student and teaching assistant at <strong>{{ t.institution }}</strong>, I have developed and maintained lecture materials, problem sets, and evaluation archives for courses ranging from introductory undergraduate sequences to advanced graduate astrophysics and cosmology.
      </p>
      <p>
        All materials are organized into modular, Overleaf-ready LaTeX templates distributed openly under the <strong>Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)</strong> license.
      </p>

      <ul class="about-links" style="margin-top: 1.5rem;">
        <li><a href="{{ t.repository_url }}" target="_blank" rel="noopener"><i class="fab fa-github" aria-hidden="true"></i> View Teaching Repository</a></li>
        <li><a href="{{ t.overleaf_url }}" target="_blank" rel="noopener"><i class="fas fa-external-link-alt" aria-hidden="true"></i> Open in Overleaf</a></li>
      </ul>
    </div>
  </div>

  <div class="about-section">
    <h3 class="section-title">Undergraduate Courses</h3>
    <div class="section-content">
      <ul class="publication-list">
        {% for course in t.undergraduate %}
        <li class="publication-entry">
          <span class="publication-entry__title">
            <a href="{{ course.github_path }}" target="_blank" rel="noopener">{{ course.code }} — {{ course.title }} ({{ course.title_es }})</a>
          </span>
          <span class="publication-entry__meta">
            {{ course.role }} · {{ course.level }} · Semesters: {{ course.semesters }}
          </span>
          <p style="margin-top: 0.5rem; font-size: 0.88rem; color: var(--color-text-secondary);">
            {{ course.description }}
          </p>
        </li>
        {% endfor %}
      </ul>
    </div>
  </div>

  <div class="about-section">
    <h3 class="section-title">Advanced & Postgraduate Courses</h3>
    <div class="section-content">
      <ul class="publication-list">
        {% for course in t.postgraduate %}
        <li class="publication-entry">
          <span class="publication-entry__title">
            <a href="{{ course.github_path }}" target="_blank" rel="noopener">{{ course.code }} — {{ course.title }} ({{ course.title_es }})</a>
          </span>
          <span class="publication-entry__meta">
            {{ course.role }} · {{ course.level }} · Semesters: {{ course.semesters }}
          </span>
          <p style="margin-top: 0.5rem; font-size: 0.88rem; color: var(--color-text-secondary);">
            {{ course.description }}
          </p>
        </li>
        {% endfor %}
      </ul>
    </div>
  </div>
</div>
