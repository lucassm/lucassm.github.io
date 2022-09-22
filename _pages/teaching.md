---
layout: archive
title: "Teaching"
permalink: /teaching/
author_profile: true
---

{% include base_path %}

<br>

{% for post in site.teaching reversed %}
    {% if post.type == teaching %}
        {% include archive-single.html %}
    {% endif %}
{% endfor %}
