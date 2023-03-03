---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* B.S. in Electrical Engineering, Federal University of Ceará (Sobral), 2013
* M.S. in Electrical Engineering, Federal University of Ceará (Fortaleza), 2015
* Ph.D in Electrical Engineering, Federal University of Ceará (Fortaleza), 2022

Work experience
======
* Summer 2015: Research Assistant
  * Github University
  * Duties included: Tagging issues
  * Supervisor: Professor Git

* Fall 2015: Research Assistant
  * Github University
  * Duties included: Merging pull requests
  * Supervisor: Professor Hub
  
Skills
======
* Power Distribution Systems Modeling
* Knowledge of the following programming languages: Python, Matlab/Octave, C/C++
* Linux Operational System 

Publications
======
  <ul>{% for post in site.publications %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
  <ul>{% for post in site.talks %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching %}
    {% if post.type != 'conteudo' %}
        {% include archive-single-cv.html %}
    {% endif %}
  {% endfor %}</ul>
  
Service and leadership
======
* Currently signed in to 43 different slack teams
