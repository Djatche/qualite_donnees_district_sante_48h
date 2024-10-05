# Améliorer la qualité des données mensuelles de district de santé en 48 heures

## Les opérations menées sont:

	- Données manquantes:
Une donnée manquante (NaN) n'est pas forcement égale à 0. Il faudra les rechercher et les remplacer par leur valeur exacte.

	- Cohérence dans le temps:    
C'est un graphique annuel linéaire. Ici les données de penta 1 pour les 12 mois des années 2000, 2001, 2002 sont affichées. On peut voir les augmentations ou les diminutions.    

	- Cohérence interne:      
7 critères ont été définit our évaluer la cohérence interne des données:

|   Critères     |      Définitions           				      	|
| :-----------	 |    :---------------------------      		      	|
|  	 	 |  Entre les vaccins administrés au même moment	       	|
|  Critère 1   	 |  penta_1 == polio_1 == pcv13_1         		       	|
|  Critère 2   	 |  penta_2 == polio_2 == pcv13_2 == rota1        		|
|  Critère 3     |  penta_3 == polio_3 == pcv13_3 == rota2 == vpi         	|
|  Critère 4     |  rr == fj         		       				|
|  	 	 |  Entre les contacts d'un même antigène	        	|
|  Critère a     |  penta_1 >= penta_2 >= penta_3         	|
|  Critère b     |  polio_1 >= polio_2 >= polio_3         	|
|  Critère c     |  pcv13_1 >= pcv13_2 >= pcv13_3            	|
|  Critère d     |  rota_1 >= rota_2         		      	|
|  	 	 |  Entre les quantités admlnistrés et les stocks restants	       	  	 		|
|  Critère 5     |  doses_administrees <= dose_utilisees       		    		  	 		|
|  	 	 |  Entre les fiches de mouvements de stock et le stock physique	  	     		|
|  Critère 6     |  stock_debut_mois == stock_fin_mois_passe       		       				|
|  Critère 7     |  (stock_debut_mois + doses_recues - doses_utilisees - doses_perdues) == stock_fin_mois       |



	- Consommation moyenne mensuelle (CMM):        
C'est une moyenne des doses administrées pour les trois derniers mois consécutifs.


## La démarche utilisée est résumée par ce graphique.    


![ Démarche itérative d'amélioration de la qualité des données ](/images/demarche_analyse.png)


## Exemples de dashboard:


Valeurs manquantes
![ Valeurs manquantes ](/images/Donnees_manquantes.png)


Cohérence interne 1
![ Quelques critère de cohérence interne ](/images/crit_1_2_3_4_a_b_c_d.png)

Cohérence interne 2
![ Quelques critère de cohérence interne ](/images/penta_crit_5_6_7.png)

Cohérence dans le temps
![ Cohérence dans le temps ](/images/coherence_dans_le_temps.png)

## les librairies utilisées sont:

	- DHIS2
	- pandas
	- numpy
	- matplotlib
	- seaborn
