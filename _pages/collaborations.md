---
title: Collaboration Network
nav_label: Collaborations
permalink: /collaborations/
nav: true
nav_order: 5
description: Explore PHCCO connections across institutions and research areas.
---

<section class="map-intro">
  <p class="themes-lead">Ideas move between laboratories, disciplines, and continents. Hover over a faculty portrait—or focus it with the keyboard—to reveal a location and open the associated profile or collaboration record.</p>
</section>

<section class="collaboration-map" aria-labelledby="faculty-map-title">
  <div class="map-heading">
    <div>
      <p class="card-label">Faculty network</p>
      <h2 id="faculty-map-title">A world of shared questions</h2>
    </div>
    <p>Vector map · faculty only</p>
  </div>
  <div class="map-stage">
    {% include world-map.html %}
    {% assign faculty = site.data.people | where: 'kind', 'faculty' %}
    {% for person in faculty %}
      {% if person.id == 'mohit-kumar-jolly' %}
        {% assign marker_href = '/faculty/mohit-kumar-jolly/' %}
        {% assign marker_action = 'View organiser profile' %}
      {% else %}
        {% assign record = site.data.collaborations | where: 'collaborator_id', person.id | first %}
        {% capture marker_href %}/collaborations/{{ record.id }}/{% endcapture %}
        {% assign marker_action = 'Open collaboration record' %}
      {% endif %}
      <a class="map-person" style="--map-x: {{ person.map_x }}%; --map-y: {{ person.map_y }}%;" href="{{ marker_href | relative_url }}" aria-label="{{ person.name }}, {{ person.map_location }}. {{ marker_action }}.">
        {% include person-photo.html person=person compact=true %}
        <span class="map-popup">
          <strong>{{ person.name }}</strong>
          <small>{{ person.map_location }}</small>
          <em>{{ marker_action }} <span aria-hidden="true">→</span></em>
        </span>
      </a>
    {% endfor %}
  </div>
  <p class="map-note">Markers indicate the institutional cities represented in this directory; portraits are offset slightly where several faculty share Bengaluru.</p>
</section>

<section class="collaboration-records" id="collaboration-records">
  <p class="card-label">Pairwise records</p>
  <h2>Collaborations with Mohit Kumar Jolly</h2>
  <p class="data-note">These records include faculty and student collaborators. The map above remains faculty-only.</p>
  <div class="collaboration-index">
  {% for collaboration in site.data.collaborations %}
    {% assign collaborator = site.data.people | where: 'id', collaboration.collaborator_id | first %}
    <a href="{{ '/collaborations/' | append: collaboration.id | append: '/' | relative_url }}">
      <strong>Mohit Kumar Jolly + {{ collaborator.name }}</strong>
      <span>{{ collaboration.focus }}</span>
    </a>
  {% endfor %}
  </div>
</section>
