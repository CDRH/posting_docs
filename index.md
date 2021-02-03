---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<link rel="stylesheet" href="/assets/css/style.css"/>

Click on a project to begin:

<div class="projects">
  {% for project in site.data.projects %}
    <a href="/projects/{{project[0]}}" class="project">
      {{ project[1].name }}
    </a>
  {% endfor %}
</div>

TODO link to datura documentation

does this work?
