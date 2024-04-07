---
layout: page
title: Meetings
permalink: /meetings/
---

Our meetings are based on the format pioneered by [NextGenBUG](http://nextgenbug.org).

Genomics Africa meetings are open to **anyone** interested in genomics or its application
in life science research and beyond. **Meetings are free** and costs covered
by the host institution. We encourage researchers in the early stages of their career
to attend and present their work. It's a great forum to practice your talks, float new ideas and approaches, and
present early work.

We welcome research presentations from industry or commercial attendees, sponsorship is also welcome.

We start meetings with a free lunch, we have two sessions with coffee somewhere in the middle. Refreshments
afterwards are served in a local pub.

We will upload presentations here:

# Upcoming Meetings

<table>
<thead>
<th>Meeting</th>
<th>Date</th>
<th>Institute</th>
<th>City</th>
</thead>
{% for meeting in site.data.meetings %}
{% if meeting.day == 'TBD' %}
{% capture day %}1{% endcapture %}
{% else %}
{% capture day %}{{meeting.day}}{% endcapture %}
{% endif %}
{% capture event_date_string %} {{ meeting.year }}-{{ meeting.month }}-{{day}} {% endcapture %}
{% capture event_date %}{{ event_date_string | date: '%s' }}{% endcapture %}
{% capture current_date %}{{ site.time | date: '%s' }}{% endcapture %}
{% if event_date >= current_date %}
<tr>
{% if meeting.page %}
<td><a href="/{{meeting.page}}">{{ meeting.meeting }}</a></td>
{% else %}
<td>{{ meeting.meeting }}</td>
{% endif %}
<td>{{ meeting.day }} {{ meeting.month }} {{ meeting.year }}</td>
<td>{{ meeting.institute }}</td>
<td>{{ meeting.city }}</td>
</tr>
{% endif %}
{% endfor %}
</table>

# Past Meetings

<table>
<thead>
<th>Meeting</th>
<th>Date</th>
<th>Institute</th>
<th>City</th>
</thead>
{% for meeting in site.data.meetings %}
{% if meeting.day == 'TBD' %}
{% capture day %}1{% endcapture %}
{% else %}
{% capture day %}{{meeting.day}}{% endcapture %}
{% endif %}
{% capture event_date_string %} {{ meeting.year }}-{{ meeting.month }}-{{day}} {% endcapture %}
{% capture event_date %}{{ event_date_string | date: '%s' }}{% endcapture %}
{% capture current_date %}{{ site.time | date: '%s' }}{% endcapture %}
{% if event_date < current_date %}
<tr>
{% if meeting.page %}
<td><a href="/{{meeting.page}}">{{ meeting.meeting }}</a></td>
{% else %}
<td>{{ meeting.meeting }}</td>
{% endif %}
<td>{{ meeting.day }} {{ meeting.month }} {{ meeting.year }}</td>
<td>{{ meeting.institute }}</td>
<td>{{ meeting.city }}</td>
</tr>
{% endif %}
{% endfor %}
</table>
