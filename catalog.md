---
layout: catalog
title: 完整目录
---

{% comment %} 

{% endcomment %}

{% assign all_pages = site.pages | sort: 'path' %}

{% assign folders = "" | split: "" %}
{% for page in all_pages %}
  {% if page.path contains '.md' and page.name != 'catalog.md' and page.name != 'index.md' %}
    {% assign dir = page.path | remove: page.name | split: '/' %}
    {% assign depth = dir.size | minus: 1 %}
    {% for i in (1..depth) %}
      {% assign folder_path = dir | slice: 0, i | join: '/' %}
      {% unless folders contains folder_path %}
        {% assign folders = folders | push: folder_path %}
      {% endunless %}
    {% endfor %}
  {% endif %}
{% endfor %}

{% assign sorted_folders = folders | sort %}

{% for folder in sorted_folders %}
  {% assign folder_pages = all_pages | where_exp: "item", "item.path contains folder" | where_exp: "item", "item.name != 'catalog.md'" | where_exp: "item", "item.name != 'index.md'" | sort: 'path' %}
  {% assign folder_name = folder | split: '/' | last %}
  {% if folder_name != "" and folder_pages.size > 0 %}
    <div class="folder">
      <div class="folder-name">📁 {{ folder_name }}</div>
      <ul class="file-list">
        {% for doc in folder_pages %}
          {% assign doc_title = doc.title | default: doc.name | replace: '.md', '' | replace: '-', ' ' %}
          <li class="file-item">
            <a class="file-link" href="https://github.com/CrescentFlux/Productivity-Engine/blob/main/{{ doc.path }}">
              <svg class="github-icon" viewBox="0 0 16 16" version="1.1">
                <path fill="#333" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0 0 16 8c0-4.42-3.58-8-8-8z"/>
              </svg>
              {{ doc_title }}
            </a>
          </li>
        {% endfor %}
      </ul>
    </div>
  {% endif %}
{% endfor %}