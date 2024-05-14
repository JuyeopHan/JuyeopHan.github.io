---
layout: archive
permalink: /publications/
author_profile: true
---

You can also find my articles on [my Google Scholar profile](https://scholar.google.com/citations?user=5Ox5W38AAAAJ)

{% include base_path %}

{% assign show_preprints = false %}
{% for post in site.publications reversed %}
  {% if post.status == "in review" %}
    {% assign show_preprints = true %}
  {% endif %}
{% endfor %}

{% if show_preprints %}
Pre-prints
======
{% endif %}
{% for post in site.publications reversed %}
  {% if post.status == "in review" %}
    {% if post.include_on_website %}
      {% include publication-single.html %}
    {% endif %}
  {% endif %}
{% endfor %}


Publications
======
{% for post in site.publications reversed %}
  {% if post.status == "published" or post.status == "to appear" or post.status == "accepted" %}
    {% unless post.type contains "thesis" %}
      {% if post.include_on_website %}
        {% include publication-single.html %}
      {% endif %}
    {% endunless %}
  {% endif %}
{% endfor %}
