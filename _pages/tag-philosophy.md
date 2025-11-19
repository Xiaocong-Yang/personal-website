---
title: "Posts tagged with: Philosophy"
permalink: /tags/philosophy/
layout: archive
author_profile: true
description: "Posts by Xiaocong Yang exploring philosophical foundations of AI, cognition, and ethics."
keywords: "philosophy of AI, ethics, Xiaocong Yang"
---

{% include base_path %}
{% assign posts = site.tags['Philosophy'] %}

{% for post in posts %}
  {% include archive-single.html %}
{% endfor %}

