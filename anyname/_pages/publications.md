---
layout: default
title: Publications
permalink: /publications/
---

<div class="pub-archive">
  {% assign publications = site.publications | sort: 'date' | reverse %}
  {% for pub in publications %}
    <div class="pub-entry">
      <div class="pub-img">
        <img src="{{ '/assets/' | append: pub.image }}" alt="{{ pub.title }}">
      </div>
      <div class="pub-meta">
        <h3 class="pub-title">
          <a href="{{ pub.external_link | default: pub.url | relative_url }}" target="_blank">
            {{ pub.title }}
          </a>
        </h3>
        <p class="pub-abstract">
            {{ pub.abstract | truncatewords: 40, "..." }}
        </p>
      </div>
    </div>
  {% endfor %}
</div>

<style>
.pub-archive {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem 1rem;
}
.pub-entry {
  display: flex;
  gap: 1rem;
  align-items: flex-start;
}
.pub-img img {
  width: 150px;
  height: auto;
  border-radius: 8px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.15);
}
.pub-meta {
  flex: 1;
}
.pub-title {
  margin: 0;
  font-size: 1.25rem;
}
.pub-title a {
  text-decoration: none;
  color: #f0f0f0;
}
.pub-title a:hover {
  text-decoration: underline;
}
.pub-abstract {
  margin-top: 0.5rem;
  color: #cccccc;
}
</style>