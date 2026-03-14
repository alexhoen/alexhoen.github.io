<h2>Prizes</h2>

<ul>
{% for link in site.data.prizes.main %}
  <li>
    <strong>{{ link.title }}</strong> - {{ link.description }}
    
    {% if link.pdf %}<a href="{{ link.pdf }}">PDF</a>{% endif %}
    {% if link.code %}<a href="{{ link.code }}">Code</a>{% endif %}
    {% if link.page %}<a href="{{ link.page }}">Link</a>{% endif %}
    {% if link.bibtex %}<a href="{{ link.bibtex }}">BibTex</a>{% endif %}
    {% if link.notes %} {{ link.notes }} {% endif %}
    {% if link.others %} {{ link.others }} {% endif %}
  </li>
{% endfor %}
</ul>
