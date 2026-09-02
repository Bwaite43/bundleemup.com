---
layout: post
title: "Drop Off Locations"
date: 2025-09-07
categories:
  - Locations
tags:
  - Plainfield
  - Danville
  - Avon
  - Brownsburg
  - Clayton
---

Drop coats off during each location's regular hours, through {{ site.data.event.collection_deadline }}.

{% for town in site.data.locations %}
### {{ town.town }}

{% for s in town.sites %}
- **{{ s.name }}**<br>{{ s.address }}
{% endfor %}
{% endfor %}
