---
layout: page
title: Members
permalink: /members/
---

Please add yourself to this page! Either [sign up here](../member_registration.html), or fork the repository, edit `_data/members.yml` and submit a pull request.

## Steering Committee

- Peter Ashton, University of York
- Jarek Bryk, University of Huddersfield
- Mark Dunning, University of Sheffield
- Dave Lunt, University of Hull
- Andrew Mason, University of York
- Krzysztof Poterlowicz, University of Bradford
- Xènia Pérez Sitjà, University of Bradford
- Lucy Stead, University of Leeds
- Emily Johnson, University of Liverpool
- Jamie Soul, University of Liverpool
- Eva Caamano Gutierrez, University of Liverpool
- Matthew Gemmell, University of Liverpool/NEOF

### PGR members of the Steering Committee

- Jess Buddle, University of Sheffield
- Deepthi Paidipati, University of Bradford
- Michael Winter, University of Hull

## Current Members

<table>
{% for member in site.data.members %}

    {% capture modulo %}{{ forloop.index | modulo: 3 }}{% endcapture %}
    {% if modulo == '1' %}
      <tr>
    {% endif %}
    <td align="center">
      {% if member.github %}
        {% avatar user=member.github size=100 %}<br>
      {% else %}
        <img src="/assets/no-github.png"><br>
      {% endif %}
      <strong>{{ member.name }}</strong>
      <p class="post-meta">{{ member.interests }}</p>
      {{ member.institute }}<br>
      {{ member.email }}<br>
      <a href="{{member.website}}">web</a> | <a href="https://twitter.com/{{member.twitter}}">twitter</a>
    </td>
    {% if modulo == '0' or forloop.last %}
      </tr>
      {% endif %}
{% endfor %}
</table>

<!---
To Add yourself to the members table:
in the data directory you need to add yourself to the members.yml file:

- github: babasaraki
  name: Umar Ahmad
  institute: Africa CDC Institute of Genomics 
  email: babasaraki@yahoo.co.uk


-->


## Alumini

<table>
{% for member in site.data.alumni %}
  {% capture modulo %}{{ forloop.index | modulo: 3 }}{% endcapture %}
    {% if modulo == '1' %}
      <tr>
    {% endif %}
    <td align="center">
      {% if member.github %}
        {% avatar user=member.github size=100 %}<br>
        {% else %}
        <img src="/assets/no-github.png"><br>
      {% endif %}
      <strong>{{ member.name }}</strong><br>
      {{ member.institute }}<br>
      {{ member.email }}<br>
      <a href="{{member.website}}">{{member.website}}</a>
     </td>
    {% if modulo == '0' or forloop.last %}
    </tr>
    {% endif %}
{% endfor %}
</table>
