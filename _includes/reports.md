<h2 id="reports" style="margin: 2px 0px -15px;">Technical Reports</h2>
<br>

<div class="reports">
<ol class="bibliography">

{% for link in site.data.reports.main %}

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
         onclick="toggleBibtex('report-bibtex{{ forloop.index }}', this)">
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

    <!-- BibTeX (hidden by default) -->
    {% if link.bibtex %}
    <div id="report-bibtex{{ forloop.index }}" class="bibtex-content">
      <button class="copy-btn" onclick="copyBibtex('report-bibtex-text{{ forloop.index }}')">Copy</button>
      <pre id="report-bibtex-text{{ forloop.index }}"><code>{{ link.bibtex }}</code></pre>
    </div>
    {% endif %}

  </div>
</div>
</li>

<br>

{% endfor %}

</ol>
</div>

<style>
/* Buttons */
.links .btn {
  font-size: 12px;
  padding: 3px 8px;
  margin-right: 5px;
  line-height: 1.2;
  display: inline-block;
  vertical-align: middle;
}

/* BibTeX box */
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
function toggleBibtex(id, btn){
  const el = document.getElementById(id);

  if (el.style.display === "block") {
    el.style.display = "none";
    btn.textContent = "BibTeX";
  } else {
    el.style.display = "block";
    btn.textContent = "Hide";
  }
}

function copyBibtex(id){
  const text = document.getElementById(id).innerText;
  navigator.clipboard.writeText(text).then(() => {
    alert("BibTeX copied!");
  });
}
</script>
