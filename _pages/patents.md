---
layout: default
title: Patents
permalink: /patents/
---

<div class="pat-archive">
  {% assign patents = site.patents | sort: 'date' | reverse %}
  {% for pat in patents %}
    <div class="pat-entry">
      <div class="pat-img">
        <a href="{{ pat.external_url | default: pat.url | relative_url }}" target="_blank">
          <img src="{{ '/assets/' | append: pat.image }}" alt="{{ pat.title }}">
        </a>
      </div>

      <div class="pat-meta">
        <h3 class="pat-title">
          <a href="{{ pat.external_url | default: pat.url | relative_url }}" target="_blank">
            {{ pat.title }}
          </a>
        </h3>
        <small class="pat-date">{{ pat.date | date: "%B %Y" }}</small>
        <!-- <p class="pat-abstract">
            {{ pat.abstract | truncatewords: 40, "..." }}
        </p> -->
      </div>
    </div>
  {% endfor %}
</div>

<style>
.pat-archive {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem 1rem;
}
.pat-entry {
  display: flex;
  gap: 1rem;
  align-items: flex-start;
}
.pat-img img {
  width: 150px;
  height: auto;
  border-radius: 8px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.15);
}
.pat-meta {
  flex: 1;
}
.pat-title {
  margin: 0;
  font-size: 1.25rem;
}
.pat-title a {
  text-decoration: none;
  color: #f0f0f0;
}
.pat-title a:hover {
  text-decoration: underline;
}
.pat-abstract {
  margin-top: 0.5rem;
  color: #cccccc;
}
</style>