---
layout: page
title: Ultras & Efforts
permalink: /ultras/
---

<p class="race-intro">A few noteworthy efforts.</p>

<div class="race-list">
{% for race in site.data.races %}
<div class="race-entry">
  <div class="race-body">
    <div class="race-text">
      <div class="race-header">
        <span class="race-name">{{ race.name }}</span>
        <span class="race-location">{{ race.location }} &middot; {{ race.date }}</span>
      </div>
      <div class="race-stats">
        {{ race.distance }}{% if race.elevation %} &middot; {{ race.elevation }} gain{% endif %} &middot; {{ race.time }}{% if race.place %} &middot; {{ race.place }}/{{ race.field }}{% endif %}
      </div>
      <p class="race-note">{{ race.note }}</p>
      <a class="race-results" href="{{ race.results_url }}" target="_blank">Receipts &rarr;</a>
    </div>
    {% if race.image %}
    <img class="race-photo" src="{{ race.image }}" alt="{{ race.name }}" {% if race.photo_pos %}style="object-position: {{ race.photo_pos }}"{% endif %}>
    {% endif %}
  </div>
</div>
{% endfor %}
</div>

<style>
.race-intro { color: #828282; margin-top: -1.25em; margin-bottom: 1.5em; }
.race-list { margin-top: 0; }
.race-entry {
  border-top: 1px solid #e8e8e8;
  padding: 1.5em 0;
}
.race-body {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 1.5em;
}
.race-text {
  flex: 1;
}
.race-photo {
  width: 200px;
  height: 200px;
  object-fit: cover;
  object-position: var(--photo-pos, center 40%);
  border-radius: 4px;
  flex-shrink: 0;
}
.race-header {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  margin-bottom: 0.4em;
}
.race-name {
  font-size: 1.1em;
  font-weight: 600;
}
.race-location {
  font-size: 0.85em;
  color: #828282;
}
.race-stats {
  font-size: 0.9em;
  color: #555;
  margin-bottom: 0.6em;
}
.race-note {
  margin-bottom: 0.6em;
  font-size: 0.95em;
}
.race-results {
  font-size: 0.85em;
}
</style>
