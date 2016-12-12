---
layout: page
title: Video
permalink: /video/ 
---

<!-- page vidéo utilisant le fichier data playlist -->

<div>

	{% for playlist in site.data.playlists %}

	 <h3 class="video-titre">{{ playlist.name }}:</h3>
	 <span class="video-date">{{ playlist.datenews }}</span>

	 <div>
   		<iframe src="{{ playlist.lien }}&amp;showinfo=0" width="560" height="315" frameborder="0" border-radius="50%" allowfullscreen> ;</iframe>
	 </div>

	 <div class="video-description">
	     <p>{{ playlist.description }}</p>
	 </div>

	{% endfor %}

</div>