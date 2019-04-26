---
layout: default
---

<table style="background-color: #dbdbdb" width = "25%">
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