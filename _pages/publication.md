---
title: "Publications"
layout: single
permalink: /publications/
author_profile: true
---

{% assign pubs = site.publications | sort: "date" | reverse %}

<ol>
{% for pub in pubs %}
  <li>
    <!-- Title -->
    <p><strong>{{ pub.title }}</strong></p>

    <!-- Authors -->
    {% if pub.authors %}
      <p>{{ pub.authors }}</p>
    {% endif %}

    <!-- Venue + year + DOI or preprint URL -->
    {% if pub.venue or pub.year or pub.doi or pub.paperurl %}
      <p><em>
        {% if pub.venue %}{{ pub.venue }}{% endif %}
        {% if pub.year %} {{ pub.year }}{% endif %}
        {% if pub.doi %}
          . DOI:
          <a href="{{ pub.doi }}" target="_blank" rel="noopener">
            {{ pub.doi }}
          </a>
        {% elsif pub.paperurl %}
          . URL:
          <a href="{{ pub.paperurl }}" target="_blank" rel="noopener">
            {{ pub.paperurl }}
          </a>
        {% endif %}
      </em></p>
    {% endif %}

    <!-- Optional BibTeX dropdown -->
    {% if pub.bibtex %}
      <details>
        <summary>BibTeX</summary>
        <pre><code>{{ pub.bibtex | escape }}</code></pre>
      </details>
    {% endif %}
  </li>
{% endfor %}
</ol>
