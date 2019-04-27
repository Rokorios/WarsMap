---
layout: default
---

<style>
@font-face {
    font-family: 'Crom';
    src: url('crom_v1-webfont.woff2') format('woff2'),
         url('crom_v1-webfont.woff') format('woff');
    font-weight: normal;
    font-style: normal;

}
</style>

<object type="image/svg+xml" data="MapSmall.svg">
  Your browser does not support SVG
</object>

<table style="font-family:Crom; position: absolute; top: 260px; left: 1000px; font-size: 0.8em; font-weight: bold;" width = "360px">
<colgroup>
<col width="190px" />
<col width="210px" />
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
