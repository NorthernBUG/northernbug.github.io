---
layout: page
title: Training
permalink: /training/
---

This page lists the training offered by members of the Genomics Africa.

{% assign sorted = site.data.training  | sort: 'date'  %}
{% for training in sorted %}

{% capture event_date %}{{ training.date | date: '%s' }}{% endcapture %}
{% capture current_date %}{{ site.time | date: '%s' }}{% endcapture %}
{% if event_date >= current_date %}
<table>
<tr>
<td style="background-color: #D3D3D3 !important; color:#FFFFFF !important;" colspan="3"><a href="{{training.link}}"><strong>{{ training.title }}</strong></a></td>
<tr style="background-color: #FFFFFF !important;">
<td colspan="3">{{ training.subtitle}}</td>
</tr>
<tr style="background-color: #FFFFFF !important;">
<td colspan="3"><strong>Description</strong><br />{{ training.description}}</td>
</tr>
<tr style="background-color: #FFFFFF !important;">
<td>{{ training.date }}</td>
<td>{{ training.duration }} day(s)</td>
<td>{{ training.institute }}</td>
</tr>

{% endif %}
{% endfor %}

