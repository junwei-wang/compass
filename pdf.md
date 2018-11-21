---
title: PDF List
layout: base
id: pdf-list
---

<h2>Lists of Cheet-Sheets</h2>
<ul style="list-style: .;">
  {% assign pdf_files = site.static_files | where: "cheetsheet", true %}
  {% for pdf in pdf_files %}
  <li><a href="{{ pdf.path }}">{{ pdf.basename }}</a></li>
  {% endfor %}
</ul>

<h2>Lists of Slides</h2>
<ul style="list-style: .;">
  {% assign pdf_files = site.static_files | where: "slides", true %}
  {% for pdf in pdf_files %}
  <li><a href="{{ pdf.path }}">{{ pdf.basename }}</a></li>
  {% endfor %}
</ul>

<h2>Lists of Resources</h2>
<ul style="list-style: .;">
  {% assign pdf_files = site.static_files | where: "resources", true %}
  {% for pdf in pdf_files %}
  <li><a href="{{ pdf.path }}">{{ pdf.basename }}</a></li>
  {% endfor %}
</ul>


<h2>Lists of All PDFs</h2>
<ul style="list-style: .;">
  {% assign pdf_files = site.static_files | where: "pdf", true %}
  {% for pdf in pdf_files %}
  <li><a href="{{ pdf.path }}">{{ pdf.path }}</a></li>
  {% endfor %}
</ul>
