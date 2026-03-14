<h2>Prizes</h2>

{% for link in site.data.prizes.main %}

{% if link.image %} {% endif %}
{% if link.conference_short %} {{ link.conference_short }} {% endif %}
<strong>{{ link.title }}</strong>
{{ link.description }}

{% if link.pdf %} PDF {% endif %}
{% if link.code %} Code {% endif %}
{% if link.page %} Link {% endif %}
{% if link.bibtex %} BibTex {% endif %}
{% if link.notes %} {{ link.notes }} {% endif %}
{% if link.others %} {{ link.others }} {% endif %}

{% endfor %}
