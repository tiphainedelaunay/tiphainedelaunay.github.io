---
layout: page
permalink: /repositories/
title: Some repos
# description: Edit the `_data/repositories.yml` and change the `github_users` and `github_repos` lists to include your own GitHub profile and repositories.
nav: true
nav_order: 3
---


{% if site.data.repositories.github_users %}
## GitHub users
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.html username=user %}
  {% endfor %}
</div>

---

{% if site.repo_trophies.enabled %}
{% for user in site.data.repositories.github_users %}
  {% if site.data.repositories.github_users.size > 1 %}
  <h4>{{ user }}</h4>
  {% endif %}
  <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% include repository/repo_trophies.html username=user %}
  </div>

  ---

{% endfor %}
{% endif %}
{% endif %}

{% if site.data.repositories.my_github_repos %}
## My own stuff
{% for repo in site.data.repositories.my_github_repos %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
    {% include repository/repo.html repository=repo %}
</div>
{% endfor %}
{% endif %}

{% if site.data.repositories.other_github_repos %}
{% for category in site.data.repositories.other_github_repos %}
## {{ category.name }}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in category.repos %}
    {% include repository/repo.html repository=repo %}
  {% endfor %}
</div>
{% endfor %}
{% endif %}
