---
layout: default
title: Members
description: Who we are
display_categories: [Current Members, Affiliates, Former Affiliates]
permalink: /members/
---


{% for category in page.display_categories %}
  <h2 class="category">{{category}}</h2>
  {% assign categorized_members = site.members | where: "category", category %}
  {% assign sorted_members = categorized_members | sort: "importance" %} <!-- can add "importance" front matter variable to each member to determine display order" -->
  {% for member in sorted_members %}
  ---
  {% include member_block.html %} <!-- MAKING THIS DOUBLE INDENT TURNS IT INTO CODE BLOCK????? -->
  {% endfor %}
{% endfor %}
