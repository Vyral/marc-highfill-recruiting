---
layout: default
title: Events
permalink: /events/
---
{% for post in site.tags["Events"] %}
<div class="row content-container">
  <!-- <div class="col-sm-12"> -->
    <h2 class="post-overview-title"><a class="post-link" href="{{ post.url }}">{{ post.title | truncate: 70 }}</a></h2>
    <!-- <span class="post-meta">
      {{ post.date | date: "%b %-d, %Y" }}
    </span> -->
      <hr />
    <!-- </div> -->

    <ul class="post-list">
<li>
  <div class="col-lg-6 post-image-container">
    <div class="post-excerpts">


      <a href="{{post.url}}">
        {% if post.use_youtube_image == true %}
        <img src="https://img.youtube.com/vi/{{post.youtube_code | remove: 'https://youtu.be/' | remove: 'https://www.youtube.com/watch?v='}}/maxresdefault.jpg" alt="{{post.title}}" class="post-image" />
        {% else %}
          {% if post.youtube_alternate_image != null %}
            <img src="{{post.youtube_alternate_image}}" alt="{{post.title}}" class="post-image"/>
          {% else %}
            <img src="{{ site.data.settings.images.post_cover }}" alt="{{post.title}}" class="post-image"/>
          {% endif %}
        {% endif %}
      </a>
    </div>
  </div>
  <div class="col-lg-6">
    {{ post.excerpt | strip_html | prepend: "<p class='excerpt'>" | append: "</p>" | truncate: 160 }}
      <p class="readlink"><a href="{{post.url}}" class="readmore">Watch Video</a></p>
  </div>
</li>
</ul>
</div>
{% endfor %}
