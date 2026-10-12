---
title: Student Network
permalink: /student-network/
nav: true
nav_order: 4
nav_label: Students
description: Student network page for PHCCO.
---

## Student directory

<p class="data-note">The first student profile uses information from the supplied reference website and Google Scholar identity.</p>

<div class="people-directory">
{% assign students = site.data.people | where: 'kind', 'student' %}
{% for person in students %}
  {% capture profile_path %}/students/{{ person.id }}/{% endcapture %}
  {% include person-card.html person=person href=profile_path %}
{% endfor %}
</div>
