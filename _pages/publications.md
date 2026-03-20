---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

You can also find my articles on [my Google Scholar profile](https://scholar.google.com/citations?user=WxQ0kSkAAAAJ).

{% include base_path %}

## Preprints

{% for post in site.publications reversed %}
  {% if post.status == "in review" %}
    {% if post.include_on_website %}
      {% include publication-single.html %}
    {% endif %}
  {% endif %}
{% endfor %}

## Publications

{% for post in site.publications reversed %}
  {% if post.status == "published" or post.status == "to appear" or post.status == "accepted" %}
    {% unless post.type contains "thesis" %}
      {% if post.include_on_website %}
        {% include publication-single.html %}
      {% endif %}
    {% endunless %}
  {% endif %}
{% endfor %}
