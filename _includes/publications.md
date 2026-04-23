## Publications

{% for link in site.data.publications.main %}

{% if link.image %}{% endif %} {% if link.conference_short %} {{ link.conference_short }} {% endif %}

<div class="title">
  <a href="{{ link.pdf }}">{{ link.title }}</a>
</div>

<div class="author">{{ link.authors }}</div>
<div class="periodical"><em>{{ link.conference }}</em></div>

<!-- Buttons -->
<div class="links">
  {% if link.pdf %}
  <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" target="_blank">PDF</a>
  {% endif %}

  {% if link.code %}
  <a href="{{ link.code }}" class="btn btn-sm z-depth-0" target="_blank">Code</a>
  {% endif %}

  {% if link.page %}
  <a href="{{ link.page }}" class="btn btn-sm z-depth-0" target="_blank">Link</a>
  {% endif %}

  {% if link.bibtex %}
  <a href="javascript:void(0);"
     class="btn btn-sm z-depth-0"
     onclick="toggleBibtex('pub-bibtex{{ forloop.index }}', this)">
    BibTeX
  </a>
  {% endif %}

  {% if link.notes %}
  <strong><i style="color:#e74d3c">{{ link.notes }}</i></strong>
  {% endif %}

  {% if link.others %}
  {{ link.others }}
  {% endif %}
</div>

<!-- BibTeX -->
{% if link.bibtex %}
<div id="pub-bibtex{{ forloop.index }}" class="bibtex-content">
  <button class="copy-btn" onclick="copyBibtex('pub-bibtex-text{{ forloop.index }}')">Copy</button>
  <pre id="pub-bibtex-text{{ forloop.index }}"><code>{{ link.bibtex }}</code></pre>
</div>
{% endif %}

{% endfor %}
