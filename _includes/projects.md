<h2 id="projects" style="margin: 2px 0px -15px;">Projects</h2>

<div class="projects">
<ol>

{% assign items = site.projects | reverse | slice: 0,10%} 
{% for project in items %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    {% if project.image %} 
    <img src="{{ project.image }}" class="teaser img-fluid z-depth-1" style="width=100;height=40%">
    {% endif %}
    {% if project.context %} 
    <abbr class="badge">{{ project.context }}</abbr>
    {% endif %}
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
    <div class="title">{{ project.title }}</div>
    <div class="description">
      {{ project.description | truncatewords: 50, '...'}}
    </div>
    <div class="footer">
      <div class="links">
      <ul>
        {% if project.extra_content %} 
        <li><a href="{{ project.url }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Continue reading</a></li>
        {% endif %}
        {% if project.code %} 
        <li><a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a></li>
        {% endif %}
        {% if project.page %} 
        <li><a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a></li>
        {% endif %}
        {% if project.note %} 
        <li><strong> <i style="color:#e74d3c">{{ project.note }}</i></strong></li>
        {% endif %}
        {% if project.others %} 
        <li>{{ project.others }}</li>
        {% endif %}
        </ul>
      </div>
      <div class="keywords">
        <ul>
            {% assign keys = project.keywords %}
            {% for key in keys %}<li>{{key}}</li>{% endfor %}
        </ul>
      </div>
    </div>
  </div>
</div>
</li>

<br>

{% endfor %}

</ol>
</div>

