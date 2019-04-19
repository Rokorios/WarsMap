---
layout: default
---

<table>
<colgroup>
<col width="30%" />
<col width="70%" />
</colgroup>
<thead>
<tr class="header">
<th>Clan</th>
<th>Territories</th>
</tr>
</thead>
<tbody>

{% for Clan in items_grouped %}

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