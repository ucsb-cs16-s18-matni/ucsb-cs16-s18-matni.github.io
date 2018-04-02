---
title: CS16, Spring 2018, zmatni
---

# {{site.course}}, {{site.quarter}}


<div id="info" data-role="collapsible" data-collapsed="false">
<h2>Course Information</h2>
<ul>
{% for item in site.info %}
<li><a href="{{item.url}}"  data-ajax="false">{{item.title }}</a></li>
{% endfor %}
</ul>
</div>

<div data-role="collapsible" data-collapsed="false">
<h2 id="lecture_notes">Lecture Notes and Slides:</h2>
{% include lecnot_table.html %}
</div>

<div data-role="collapsible" data-collapsed="false">
<h2 id="homework">Homework:</h2>
<p>NOTE: All homework is taken on GauchoSpace</p>
{% include hwk_table.html %}
</div>

<div data-role="collapsible" data-collapsed="false">
<h2 id="labs">Labs:</h2>
<p>NOTE: All labs must be submited on submit.cs </p>
{% include lab_table.html %}
</div>

<!--
<div data-role="collapsible" data-collapsed="false">
<h2 id="exams">Exams</h2>
-->

[comment]: # %include exam_table.html %

<!-- 
</div>
-->
