<h2 id="publications" style="margin: 2px 0px -15px;">Publications</h2>

<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}

<li>
  <div class="pub-row">
  
    <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
  
      {% if link.image %} 
      <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width:100%;height:auto;">
      {% endif %}
    
      {% if link.conference_short %} 
      <abbr class="badge">{{ link.conference_short }}</abbr>
      {% endif %}
  
    </div>
  
    <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">

      <div class="title">
      <a href="{{ link.pdf }}">{{ link.title }}</a>
      </div>

      <div class="author">
      {{ link.authors }}
      </div>

      <div class="periodical">
      <em>{{ link.conference }}</em>
      </div>
        
        <div class="links">
        
        {% if link.pdf %} 
        <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" target="_blank" style="font-size:12px;">PDF</a>
        {% endif %}
        
        {% if link.code %} 
        <a href="{{ link.code }}" class="btn btn-sm z-depth-0" target="_blank" style="font-size:12px;">Code</a>
        {% endif %}
        
        {% if link.page %} 
        <a href="{{ link.page }}" class="btn btn-sm z-depth-0" target="_blank" style="font-size:12px;">Link</a>
        {% endif %}
        
        {% if link.bibtex %}
        <button 
        class="btn btn-sm z-depth-0"
        style="font-size:12px;"
        onclick="toggleBibtex('bibtex{{ forloop.index }}')">
        BibTeX
        </button>
        {% endif %}
        
        {% if link.notes %} 
        <strong><i style="color:#e74d3c">{{ link.notes }}</i></strong>
        {% endif %}
        
        </div>
        {% if link.bibtex %}
          <div id="bibtex{{ forloop.index }}" class="bibtex-content">
            <pre><code>{{ link.bibtex }}</code></pre>
          </div>
        {% endif %}

    </div>

  </div>
</li>

{% endfor %}

</ol>
</div>

<script>
function toggleBibtex(id){
  var el = document.getElementById(id);
  if(el.style.display === "block"){
    el.style.display = "none";
  } else {
    el.style.display = "block";
  }
}
</script>
