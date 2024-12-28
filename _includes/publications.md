<h2 id="publications" style="margin: 2px 0px -15px;">Publications</h2>

<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    {% if link.image %} 
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width=100;height=40%">
    {% endif %}
    {% if link.conference_short %} 
    <abbr class="badge">{{ link.conference_short }}</abbr>
    {% endif %}
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
      <div class="title"><a href="{{ link.pdf }}">{{ link.title }}</a></div>
      <div class="author">{{ link.authors }}</div>
      <div class="periodical"><em>{{ link.conference }}</em>
      </div>
    <div class="links">
      {% if link.pdf %} 
      <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
      {% endif %}
      {% if link.code %} 
      <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
      {% endif %}
      {% if link.page %} 
      <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Link</a>
      {% endif %}
      {% if link.bibtex %} 
      <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
      {% endif %}
      {% if link.notes %} 
      <strong> <i style="color:#e74d3c">{{ link.notes }}</i></strong>
      {% endif %}
      {% if link.others %} 
      {{ link.others }}
      {% endif %}
    </div>
     <!-- Expand Button -->
  <button onclick="toggleBibtex('bibtex1')">BibTeX</button>
  
  <!-- Hidden BibTeX content -->
  <div id="bibtex1" style="display: none; margin-top: 10px; background-color: #f9f9f9; padding: 10px; border: 1px solid #ddd;">
    <pre>
      @article{example2024,
      title={An example article},
      author={Doe, John and Smith, Jane},
      journal={Example Journal},
      year={2024},
      volume={42},
      pages={123--456},
    }
    </pre>
  </div>
  </div>
</div>
</li>

<br>

{% endfor %}

</ol>
</div>

<script>
  function toggleBibtex(id) {
    const bibtexDiv = document.getElementById(id);
    if (bibtexDiv.style.display === "none") {
      bibtexDiv.style.display = "block";
    } else {
      bibtexDiv.style.display = "none";
    }
  }
</script>

