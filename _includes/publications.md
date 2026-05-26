<h2 id="publications" style="margin: 2px 0px -15px;">Publications</h2>

<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}
<li>
  <div class="pub-row">

    <!-- Left column -->
    <div class="col-sm-3 abbr" style="padding: 0 15px;">
      {% if link.image %}
      <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width:100%;height:auto;">
      {% endif %}
      {% if link.conference_short %}
      <abbr class="badge">{{ link.conference_short }}</abbr>
      {% endif %}
    </div>

    <!-- Right column -->
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
        <a href="javascript:void(0);" 
           class="btn btn-sm z-depth-0 bibtex-btn"
           onclick="toggleBibtex(this)">
           BibTeX
        </a>
        {% endif %}

        {% if link.notes %}
        <strong><i style="color:#e74d3c">{{ link.notes }}</i></strong>
        {% endif %}
      </div>

      <!-- BibTeX (hidden by default) -->
      {% if link.bibtex %}
      <div class="bibtex-content">
        <button class="copy-btn" onclick="copyBibtex(this)">Copy</button>
        <pre>{{ link.bibtex }}</pre>
      </div>
      {% endif %}

    </div>
  </div>
</li>
{% endfor %}

</ol>
</div>

<style>
/* Remove default list indentation */
.publications ol {
  list-style: decimal;
  list-style-position: inside;
  padding-left: 0;
  margin-left: 0;
}

.publications li {
  margin-left: 0;
  padding-left: 0;
}

/* Row alignment (remove Bootstrap gutter offset) */
.pub-row {
  margin-left: 0;
  margin-right: 0;
}

/* Remove column padding for flush layout */
.pub-row > div {
  padding-left: 0 !important;
  padding-right: 0 !important;
}

/* Optional: add small spacing between entries */
.publications li {
  margin-bottom: 12px;
}

/* Buttons */
.links .btn {
  font-size: 12px;
  padding: 3px 8px;
  margin-right: 5px;
  line-height: 1.2;
  display: inline-block;
  vertical-align: middle;
}

/* BibTeX hidden initially */
.bibtex-content {
  display: none;
  margin-top: 6px;
  background: #f8f9fa;
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 10px;
  position: relative;
}

/* Copy button */
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

/* Code block */
.bibtex-content pre {
  margin: 0;
  font-size: 12px;
  overflow-x: auto;
  padding-right: 60px;
}
</style>
<script>
function toggleBibtex(btn){
  const container = btn.closest('.pub-row');
  const bib = container.querySelector('.bibtex-content');

  if (!bib) return;

  const isVisible = bib.style.display === "block";
  bib.style.display = isVisible ? "none" : "block";
  btn.textContent = isVisible ? "BibTeX" : "Hide";
}

function copyBibtex(btn){
  const container = btn.closest('.bibtex-content');
  const text = container.querySelector('pre').innerText;

  navigator.clipboard.writeText(text).then(() => {
    btn.textContent = "Copied!";
    setTimeout(() => btn.textContent = "Copy", 1200);
  });
}
</script>
