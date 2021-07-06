---
layout: page
permalink: /news/
title: news
description: General updates of my study, research and publications.
nav: true
order: 3
---

<div class="news">
  {% if site.news  %}
    <div class="table-responsive">
      <table class="table table-sm table-borderless">
      {% assign news = site.news | reverse %}
      {% assign last_item_year = "now" | date: "%Y" %}
      {% for item in news %}
        <tr>
          <th scope="row" style='width: 100px;'>{{ item.date | date: "%b %-d, %Y" }}</th>
          <td>
            {% if item.inline %}
            {% if item.new %} <mark><i>new</i></mark> {% endif %} {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
            {% else %}
              <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
            {% endif %}
          </td>
        </tr>
      {% endfor %}
      </table>
    </div>
  {% else %}
    <p>No news so far...</p>
  {% endif %}
</div>
