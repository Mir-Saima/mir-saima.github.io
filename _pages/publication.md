---
title: "Publications"
permalink: /publications/
layout: default
author_profile: true
---

<h1>Publications</h1>

<ol class="bibliography">
{% assign pubs = site.publications | sort: 'year' | reverse %}
{% for pub in pubs %}
  <li>
 {% for pub in pubs %}
  <li style="margin-bottom: 1.2em;">
    
    <!-- Title -->
    {% if pub.title %}
      <strong style="font-size: 1.1em;">{{ pub.title }}</strong><br>
    {% endif %}

    <!-- Authors -->
    {% if pub.authors %}
      <span style="color: #555;">{{ pub.authors }}</span><br>
    {% endif %}

    <!-- Venue + Year + DOI -->
    {% if pub.venue or pub.year or pub.doi %}
      <span>
        {% if pub.venue %}<em>{{ pub.venue }}</em>{% endif %}
        {% if pub.year %} {{ pub.year }}.{% endif %}
        {% if pub.doi %}
          DOI: <a href="{{ pub.doi }}">{{ pub.doi }}</a>.
        {% endif %}
      </span>
    {% endif %}

    <!-- BibTeX Dropdown -->
    {% if pub.bibtex %}
      <details style="margin-top: .3em;">
        <summary>BibTeX</summary>
        <pre><code>{{ pub.bibtex | escape }}</code></pre>
      </details>
    {% endif %}

  </li>
{% endfor %}

  </li>
{% endfor %}
</ol>
