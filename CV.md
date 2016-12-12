---
layout: pagecv
title: C.V
permalink: /CV/
---
<div class="cv">

 <img src="{{ site.baseurl }}/img/cv/photo.png" class="cv-img"> <!-- image de fond -->

  {% for cv in site.data.CV%}
   <div class="cv-nom">
     <h2>{{ cv.nom }}<br>{{ cv.prenom }}<br>{{ cv.email }}</h2>
   </div>
   <div class="cv-part1">
     <p><span class="cv-objactu">Mon objectif:</span> {{ cv.objectif }}</p>
     <p><span class="cv-objactu"> Actuellement:</span> {{ cv.actuellement }}</p>
   </div>

   <h2 class="cv-titre">Expérience Professionnelles </h2>

   <!-- Boucle de donnés de la partie profession -->

   {% for exp-pro in cv.profession %}   
     <ul>
  	   <li> <span class="cv-date">{{ exp-pro.date }}:</span> {{ exp-pro.employeur }}, {{ exp-pro.ville }} {{ exp-pro.metier }} {% if exp-pro.poste %}<br> <span class="cv-marge"> Poste: {{exp-pro.poste}}</span>{% endif %} 
   		   <ul>
           {% if exp-pro.boulangerie %} 
            <li class="cv-marge">Poste effectuer en boulangerie: {{ exp-pro.boulangerie }}</li>
           {% endif %}
    	     {% if exp-pro.patisserie %} 
            <li class="cv-marge">Poste effectuer en pâtisserie: {{ exp-pro.patisserie }}</li>
           {% endif %}
   		   </ul>
    	 </li>
     </ul>
   {% endfor %}

   <h2 class="cv-titre">Formation</h2>

   <!-- Boucle de donnés de la partie formation -->

   {% for forma in cv.formation %}
     <ul>
  	   <li>
         <span class="cv-date">{{ forma.date }}:</span> {{ forma.ecole }}, {{ forma.ville }}<br><span class="cv-marge">Diplôme: {{ forma.diplome }}</span>
       </li>
     </ul>
   {% endfor %}

   <h2 class="cv-titre">Centre d'intérêt</h2>
  
   <!-- Boucle de donnés de la partie centre d'intérêt -->

    <div class="cv-flex">

      {% for inter in cv.centre-interet %}
       <div>
          <ul>
           {% if inter.loisir %}
  	  	    <li>
  		        <span class="cv-date">Loisir:</span>
  	 	         {% for loisir in inter.loisir %}
  	  	  	    <ul>
  		  		      <li>{{ loisir.nom }}:</li>
      		      </ul>
     	         {% endfor %}
      	    </li>
    	     {% endif %}
          </ul>	   
       </div>
       <div>
         <ul>
    	    {% if inter.sport %}    	
        	 <li>
  		      <span class="cv-date">Sport:</span>
  	 	      {% for sport in inter.sport %}
  	  		   <ul>
  		  	  	<li>
               <span class="cv-date-sport">{{ sport.date }}:</span> {{ sport.nom }} au club de {{ sport.ville }}:
              </li>
     		     </ul>
     		    {% endfor %}
    	     </li>		
		      {% endif %}
         </ul>
        </div>
      {% endfor %}
    </div>
 {% endfor %}
</div>
