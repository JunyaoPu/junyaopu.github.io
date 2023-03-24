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

As an <b>AI researcher and developer</b>, I specialize in creating <b>real-time AI vision systems</b> for edge hardware, specifically for the <b>NVIDIA Jetson family</b>. My work involves leveraging cutting-edge deep learning techniques to build efficient and effective computer vision algorithms that can operate on resource-constrained devices. In addition, I have a keen interest in <b>large language models</b> and <b>generative AI</b>, and enjoy exploring the possibilities they offer for enhancing human-machine interactions.

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
