---
layout: page
title: Research
permalink: /research/
description: My research interests and academic work.
nav: true
nav_order: 2
---

<div class="research-content">
  <h2>Research Interests</h2>
  <p>My academic interests focus on several key areas in computer science:</p>

  <div class="research-areas">
    <div class="research-area">
      <h3>Machine Learning & Artificial Intelligence</h3>
      <p>Exploring the theoretical foundations and practical applications of ML algorithms, including deep learning, neural networks, and pattern recognition.</p>
    </div>

    <div class="research-area">
      <h3>Software Engineering</h3>
      <p>Studying software development methodologies, system design, and the creation of scalable, maintainable software solutions.</p>
    </div>

    <div class="research-area">
      <h3>Data Structures & Algorithms</h3>
      <p>Investigating efficient algorithms and data structures for solving complex computational problems.</p>
    </div>
  </div>

  <h2>Current Work</h2>
  <p>As a senior student, I am actively engaged in coursework and research projects that bridge theoretical knowledge with practical implementation. I am particularly interested in applying machine learning techniques to real-world problems and contributing to open-source software development.</p>

  <h2>Future Goals</h2>
  <p>I aim to pursue graduate studies in computer science, focusing on the intersection of artificial intelligence and software engineering. My goal is to contribute to research that has meaningful impact on society while advancing the field of computer science.</p>
</div>

<style>
.research-content {
  max-width: 800px;
  margin: 0 auto;
}

.research-areas {
  margin: 2rem 0;
}

.research-area {
  background-color: #f8f9fa;
  padding: 1.5rem;
  margin-bottom: 1rem;
  border-radius: 8px;
  border-left: 4px solid #007bff;
}

.research-area h3 {
  color: #007bff;
  margin-top: 0;
}

.research-area p {
  margin-bottom: 0;
}

h2 {
  color: #333;
  margin-top: 2rem;
  margin-bottom: 1rem;
}

h2:first-child {
  margin-top: 0;
}
</style>
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
