<h2 id="publications" style="margin: 2px 0px -15px;">Publications</h2>

<div class="publications">
<ol class="bibliography">

<h2 id="publications" style="margin: 2px 0px -15px;">Publications</h2>

<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}

<li>
<div class="pub-row">

  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">

```
{% if link.image %} 
<img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width:100%;height:auto;">
{% endif %}

{% if link.conference_short %} 
<abbr class="badge">{{ link.conference_short }}</abbr>
{% endif %}
```

  </div>

  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">

```
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
    <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
    {% endif %}

    {% if link.code %} 
    <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
    {% endif %}

    {% if link.page %} 
    <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Link</a>
    {% endif %}

    {% if link.notes %} 
    <strong><i style="color:#e74d3c">{{ link.notes }}</i></strong>
    {% endif %}

    {% if link.others %} 
    {{ link.others }}
    {% endif %}

  </div>


  <!-- BibTeX Dropdown -->
  {% if link.bibtex %}
  <div class="bibtex-box">

    <button 
      class="bibtex-toggle btn btn-sm z-depth-0"
      onclick="toggleBibtex('bibtex{{ forloop.index }}')">
      BibTeX ▼
    </button>

    <div id="bibtex{{ forloop.index }}" class="bibtex-content">

      <button 
        class="copy-btn"
        onclick="copyBibtex('bibtex-text{{ forloop.index }}')">
        Copy
      </button>
```

<pre id="bibtex-text{{ forloop.index }}"><code>{{ link.bibtex }}</code></pre>

```
    </div>

  </div>
  {% endif %}
```

  </div>
</div>
</li>

<br>

{% endfor %}

</ol>
</div>

<style>

.bibtex-box{
  margin-top:8px;
}

.bibtex-toggle{
  font-size:12px;
  cursor:pointer;
}

.bibtex-content{
  display:none;
  margin-top:10px;
  background:#f8f9fa;
  border:1px solid #e1e4e8;
  border-radius:6px;
  padding:12px;
  position:relative;
  animation:fadeIn 0.25s ease-in-out;
}

.bibtex-content pre{
  margin:0;
  font-size:12px;
  overflow-x:auto;
}

.copy-btn{
  position:absolute;
  right:10px;
  top:8px;
  font-size:11px;
  border:none;
  background:#eaecef;
  padding:4px 8px;
  border-radius:4px;
  cursor:pointer;
}

.copy-btn:hover{
  background:#d0d7de;
}

@keyframes fadeIn{
  from{opacity:0; transform:translateY(-4px);}
  to{opacity:1; transform:translateY(0);}
}

</style>

<script>

function toggleBibtex(id){
  const el = document.getElementById(id);

  if(el.style.display === "block"){
    el.style.display = "none";
  } 
  else{
    el.style.display = "block";
  }
}

function copyBibtex(id){
  const text = document.getElementById(id).innerText;

  navigator.clipboard.writeText(text).then(()=>{
    alert("BibTeX copied!");
  });
}

</script>

