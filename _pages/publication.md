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
    <p>
      {% if pub.authors %}{{ pub.authors }}.{% endif %}
      {% if pub.title %} <strong>{{ pub.title }}</strong>.{% endif %}
      {% if pub.venue %} <em>{{ pub.venue }}</em>.{% endif %}
      {% if pub.year %} {{ pub.year }}.{% endif %}
      {% if pub.doi %}
        DOI: <a href="{{ pub.doi }}">{{ pub.doi }}</a>.
      {% endif %}
    </p>

    {% if pub.bibtex %}
      <details>
        <summary>BibTeX</summary>
        <pre><code>{{ pub.bibtex | escape }}</code></pre>
      </details>
    {% endif %}
  </li>
{% endfor %}
</ol>
