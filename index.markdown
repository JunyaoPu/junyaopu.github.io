---
#excerpt: "Exploring graphics, simulation and AI"
header:
    overlay_image: /assets/images/ferro_header_compressed.jpg
    overlay_filter: 0.5
    show_overlay_excerpt: false
    image_description: "Moving Forward with Anticipation."
    caption: "Moving Forward with Anticipation."
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

I am working in <b>AI research and development</b>, with a focus on creating real-time computer vision systems for edge hardware such as the NVIDIA Jetson family. Additionally, I have a strong interest in <b>natural language processing</b> and <b>generating simulated images and videos</b> using AI technology.

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
