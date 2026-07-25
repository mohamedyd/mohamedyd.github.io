---
layout: page
permalink: /repositories/
title: Repositories
description: A snapshot of selected open-source repositories.
nav: true
nav_order: 4
---

<p class="text-center">
  Selected open-source repositories. Full profile at
  <a href="{{ site.data.repositories.github_profile }}" target="_blank" rel="noopener noreferrer">github.com/{{ site.data.repositories.github_username }}</a>.
</p>

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-stretch">
  {% for repo in site.data.repositories.repositories %}
    <div class="repo p-2">
      <a href="{{ repo.url }}" target="_blank" rel="noopener noreferrer">
        <div class="card hoverable h-100">
          <div class="card-body">
            <h5 class="card-title mb-2"><i class="fa-brands fa-github mr-2"></i>{{ repo.name }}</h5>
            {% if repo.description %}<p class="card-text mb-2">{{ repo.description }}</p>{% endif %}
            <div style="font-size: 0.8rem; color: var(--global-text-color-light);">
              {% if repo.language %}<span class="mr-3">{{ repo.language }}</span>{% endif %}
              <span class="mr-3"><i class="fa-solid fa-star"></i> {{ repo.stars }}</span>
              <span><i class="fa-solid fa-code-fork"></i> {{ repo.forks }}</span>
            </div>
          </div>
        </div>
      </a>
    </div>
  {% endfor %}
</div>
