---
title: Faculty Network
permalink: /faculty-network/
nav: true
nav_order: 3
nav_label: Faculty
description: Faculty network page for PHCCO.
---

## Faculty directory

<p class="data-note">Faculty profiles use the supplied Google Scholar identities. Fields that Scholar does not provide remain explicitly marked for verification.</p>

<div class="people-directory">
{% assign faculty = site.data.people | where: 'kind', 'faculty' %}
{% for person in faculty %}
  {% capture profile_path %}/faculty/{{ person.id }}/{% endcapture %}
  {% include person-card.html person=person href=profile_path %}
{% endfor %}
</div>
