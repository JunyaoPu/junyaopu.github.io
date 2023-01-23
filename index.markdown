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
I am interested in <b>AI research & development</b> for real-world problems. I've studied <b>deep learning, numerical simulation, and tensorization methods</b>. I've explored advanced deep learning algorithms and led AI projects for <b> off-highway autonomous systems</b>.
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
