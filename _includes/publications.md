<h2 id="publications" style="margin: 2px 0px -15px;">Publications</h2>

<div class="publications">
<ol class="bibliography">


{% for link in site.data.publications.main %}
<li>
  <div class="pub-row">

    <!-- Left column: image / badge -->
    <div class="col-sm-3 abbr" style="padding: 0 15px;">
      {% if link.image %}
      <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width:100%;height:auto;">
      {% endif %}
      {% if link.conference_short %}
      <abbr class="badge">{{ link.conference_short }}</abbr>
      {% endif %}
    </div>

    <!-- Right column: title, authors, buttons -->
    <div class="col-sm-9" style="padding: 0 20px;">
      <div class="title">
        <a href="{{ link.pdf }}">{{ link.title }}</a>
      </div>
      <div class="author">{{ link.authors }}</div>
      <div class="periodical"><em>{{ link.conference }}</em></div>

      <!-- Buttons -->
      <div class="links">
        {% if link.pdf %}
        <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0">PDF</a>
        {% endif %}
        {% if link.code %}
        <a href="{{ link.code }}" class="btn btn-sm z-depth-0">Code</a>
        {% endif %}
        {% if link.page %}
        <a href="{{ link.page }}" class="btn btn-sm z-depth-0">Link</a>
        {% endif %}
        {% if link.bibtex %}
        <button class="btn btn-sm z-depth-0 bibtex-btn">BibTeX</button>
        {% endif %}
        {% if link.notes %}
        <strong><i style="color:#e74d3c">{{ link.notes }}</i></strong>
        {% endif %}
      </div>

      <!-- BibTeX content: visible by default -->
      {% if link.bibtex %}
      <div class="bibtex-content">
        <button class="copy-btn" onclick="copyBibtex('bibtex-text{{ forloop.index }}')">Copy</button>
        <pre id="bibtex-text{{ forloop.index }}"><code>{{ link.bibtex }}</code></pre>
      </div>
      {% endif %}

    </div>
  </div>
</li>
{% endfor %}

</ol>
</div>

<style>
/* Button spacing and size */
.links .btn, .bibtex-btn {
  font-size: 12px;
  padding: 3px 8px;
  margin-right: 5px;
}

/* BibTeX box visible by default */
.bibtex-content {
  display: block; /* visible immediately */
  margin-top: 5px;
  background: #f8f9fa;
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 10px;
  width: 100%;
  box-sizing: border-box;
  position: relative;
}

/* Copy button inside BibTeX box */
.copy-btn {
  position: absolute;
  top: 8px;
  right: 10px;
  font-size: 11px;
  padding: 4px 8px;
  border: none;
  border-radius: 4px;
  background: #eaecef;
  cursor: pointer;
}

.copy-btn:hover {
  background: #d0d7de;
}

/* Optional: style pre/code */
.bibtex-content pre {
  margin: 0;
  font-size: 12px;
  overflow-x: auto;
  padding-right: 60px; /* space for copy button */
}
</style>

<script>
function copyBibtex(id){
  const text = document.getElementById(id).innerText;
  navigator.clipboard.writeText(text).then(() => {
    alert("BibTeX copied!");
  });
}
</script>
