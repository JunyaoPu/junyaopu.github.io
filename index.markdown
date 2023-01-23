---
#excerpt: "Exploring graphics, simulation and AI"
header:
    overlay_image: /assets/images/ferro_header_compressed.jpg
    overlay_filter: 0.5
    show_overlay_excerpt: false
    image_description: "2D ferrofluid simulation from my thesis project."
    caption: "Simulation of the Rosensweig instability."
    actions:
    - label: "Projects"
      url: /projects/
    - label: "About"
      url: /about/
layout: single
author_profile: true
classes: wide

collection: projects
entries_layout: list
---

<div class="quoty-text">
I work at the intersection of <b>physics, math and computer science</b> researching <b> simulation, computer graphics and AI</b>.
</div>
<hr>
<div>
<h3 style="margin-top: 0em;">{{ site.data.ui-text[site.locale].recent_posts | default: "Recent Posts" }}</h3>
{% if paginator %}
  {% assign posts = paginator.posts %}
{% else %}
  {% assign posts = site.posts %}
{% endif %}
{% for post in posts %}
  {% include archive-single.html %}
{% endfor %}
{% include paginator.html %}
</div>
