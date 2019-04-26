---
layout: default
---

<object type="image/svg+xml" data="Map.svg">
  Your browser does not support SVG
</object>

<table style="background-color: #dbdbdb; position: absolute; top: 400px; left: 1750px; font-size: 30; font-weight: bold;" width = "1000px">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Clan</th>
<th>Territories</th>
</tr>
</thead>
<tbody>

{% assign items_grouped = site.data.ConanManifest | group_by: 'Owner' %}
{% assign items_sorted = items_grouped | sort: 'name' %} 
{% for Clan in items_sorted %}

	<tr>
	<td style="color:{{Clan.items[0].Color}}">{{ Clan.name }}</td>
	<td style="color:{{Clan.items[0].Color}}">
	{% for Territory in Clan.items %}
		{{Territory.Territory}} 
	{% endfor %}
	</td>
	</tr>
	
{% endfor %}

</tbody>
</table>