---
layout: archive
title: "Teaching"
permalink: /teaching/
author_profile: true
---

{% include base_path %}

<br>

# Horários Disponíveis para atendimento

> **Quartas e Sextas das 14h as 18h**. Agendar o atendimento com antecedência, de preferência via mensagem de e-mail (lucassmelo@dee.ufc.br).

# Disciplinas sendo ministradas no semestre 2021.1


{% for post in site.teaching reversed %}
  {% if post.type == teaching %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}
