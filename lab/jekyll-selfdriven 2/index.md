---
layout: default
title: Areas of Focus
description: A structured framework for decentralised governance — distributing responsibility across interconnected domains.
---

<section class="hero">
  <p class="hero-eyebrow">selfdriven Foundation &mdash; Framework</p>
  <h1>Eight <em>Areas</em><br>of Focus</h1>
  <p class="hero-desc">
    A structured framework for decentralised governance — distributing responsibility
    across interconnected domains so that communities can self-actuate with clarity,
    integrity, and resilience.
  </p>
</section>

<section class="stats" aria-label="Framework at a glance">
  <div class="stat">
    <div class="stat-num"><span>8</span></div>
    <div class="stat-label">Areas of Focus<br>across the organisation</div>
  </div>
  <div class="stat">
    <div class="stat-num"><span>1</span></div>
    <div class="stat-label">Shared mission<br>community self-actuation</div>
  </div>
  <div class="stat">
    <div class="stat-num">∞</div>
    <div class="stat-label">Interconnections<br>between every area</div>
  </div>
</section>

<section class="grid-section" aria-label="Areas of Focus grid">
  <div class="grid-section-header">
    <h2>Explore the Framework</h2>
    <span>Click any area for detail</span>
  </div>

  <div class="areas-grid">
    {% for area in site.data.areas %}
    <div class="area-card" data-id="{{ area.id }}" role="button"
         tabindex="0" aria-label="Learn about {{ area.title }}"
         onkeydown="if(event.key==='Enter'||event.key===' ')this.click()">
      <div class="area-card-header">
        <div class="area-title">{{ area.title }}</div>
        <div class="area-num">{{ area.id | prepend: '0' | slice: -2, 2 }}</div>
      </div>
      <p class="area-subtitle">{{ area.subtitle }}</p>
      <span class="area-arrow">→</span>
    </div>
    {% endfor %}
  </div>
</section>

<div class="detail-panel" id="detailPanel" role="region" aria-label="Area detail" aria-live="polite">
  <div class="detail-inner">
    <div class="detail-header">
      <div class="detail-num" id="detailNum">01</div>
      <button class="detail-close" id="detailClose" aria-label="Close detail">✕</button>
    </div>
    <h2 class="detail-title" id="detailTitle"></h2>
    <p class="detail-tagline" id="detailTagline"></p>
    <p class="detail-body" id="detailBody"></p>
  </div>
</div>

<section class="connections-section" style="margin-top: 48px;">
  <div class="connections-inner">
    <p class="section-label">Interconnections</p>
    <h2>Each Area Informs the Next</h2>
    <p>
      The eight areas are not silos — they form an interconnected system. Direction shapes what
      Engagement communicates. Engagement surfaces what Enablement must build. Enablement depends
      on the Protocols it implements. Protocols demand Sustainability. Sustainability drives efficient
      Processes. Processes enable Accountability. Accountability feeds back into Direction.
    </p>
    <div class="flow-row">
      {% for area in site.data.areas %}
      <span class="flow-node">{{ area.title }}</span>
      {% unless forloop.last %}<span class="flow-arrow">→</span>{% endunless %}
      {% endfor %}
    </div>
  </div>
</section>

<!-- Pass areas data to JS -->
<script>
window.AREAS_DATA = {
  {% for area in site.data.areas %}
  {{ area.id }}: {
    title:   {{ area.title | jsonify }},
    tagline: {{ area.tagline | jsonify }},
    body:    {{ area.body | jsonify }}
  }{% unless forloop.last %},{% endunless %}
  {% endfor %}
};
</script>
