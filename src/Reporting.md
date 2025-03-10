# Rapport d'Analyse - Call Center Project

## 1. Introduction:
Dans le cadre de l'analyse de données d'un centre d'Appels, nous avons entrepris une exploration et une analyse minutieuse des valeurs dans le but de détecter les périodes de rush ou de forte activités du Centre d'Appels et les facteurs qui influencent le nombre d'appels abandonnés pour optimiser les performance du Centre d'Appels.

## 2. Objectif du rapport:

L'analyse vise à répondre aux questions suivantes:
  - Quelles sont les périodes de rush ou de forte affluence ?
  - Comment optimiser les services du Centre d'Appels pour améliorer la satisfaction de nos clients ?
  - Quels sont les facteurs qui influencent le nombre d'appels abandonnés ?

## 3. Aperçu des données utilisées:

L'analyse est basée sur les données d'un centre d'appels qui couvre l'année 2021.
Les principales métriques, qui ont constitué le socle, la pierre angulaire de mes analyses sont:

- `incoming_calls`: le nombre d'appels entrants, soit tous les appels que le centre d'appels a reçus.

- `answered_calls`: le nombre d'appels qui ont été répondus par nos agents.

- `abandoned_calls`: le nombre d'appels où l'appelant a raccroché avant de parler à un agent.

- `answer_speed(seconds)`: Le temps moyen en secondes que les agents ont mis pour répondre aux appels après que ces derniers aient été reçus.

- `waiting_time(seconds)`: Le temps moyen en secondes que les appelants ont passé en attente avant qu'un agent ne réponde.

- `talk_duration(seconds)`: Le temps moyen en secondes des conversations entre les agents et les appelants.



## 4. **Visualisation des tendances et des performances: Analyse Graphiques**
### 4.1 Introduction:

Dans cette section, nous explorons les données du centre d'appels à travers des visualisations graphiques afin de mettre en évidence les tendances, les distributions et les relations entre les différentes métriques clés. Les graphiques permettent une compréhension visuelle des comportements observés comme les périodes de forte activité, les variations de performance en fonction des jours ou des mois, et les éventuelles corrélations entre variables.

### 4.2 Graphiques montrant la distribution des variables clés:
 #### 1- Histogrammes pour les variables continues:
	- Distribution des appels entrants:
![**Distribution des appels entrants**](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/3a79ce3eb0af52812e4f9ab45c8fa92303f4cad0/src/graphes/incoming_calls_dist.png)
	- _**Ce graphique nous montre le nombre d'appels que le centre d'appels reçoit par jour, il semble assez clair que la plupart des jours le nombre d'appels se situe entre 100 et 200.**_
 
	- Distribution des appels abandonnés:
 ![**Distribution des appels abandonnés**](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/3165ef2fe2985f1ed97070853da0b57124a717e2/src/graphes/abandoned_dist.png)
 	- _**Ce graphique indique combien de personnes raccrochent avant de parler à un agent. La majorité des abandons se produit avant 20 secondes d'attente. Néanmoins il faut noter quelques valeurs anormales au delà de 40 secondes**_

	- Distribution de la vitesse de réponse:
 ![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/3165ef2fe2985f1ed97070853da0b57124a717e2/src/graphes/answer_time_dist.png)
 	- _**Cette visualisation nous montre le temps moyen que les agents prennent pour répondre aux appels. En général, les appels reçoivent une réponse entre 10 et 25 secondes.**_

 #### 2- Segmentation des variables clés temporellement(par mois et par jour):
	- Volume des appels entrants par mois:
 ![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/21d6504d5d381a5af688522a8d685dd50c0bbd28/src/graphes/incoming_calls_month%20(2).png)
 	- _**Ici on analyse le nombre total d'appels reçus chaque mois. Les mois de décembre et octobre ont les volumes d'appels les plus élevés, tandis que le mois de juin a le volume le plus faible.**_

 	- Volume des appels entrants par jour:
  ![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/695425f471cb3094a2b3d792be4eab78a599b2fe/src/graphes/incoming_calls_day.png)
	- _**Ce graphique montre les appels entrants par jour de la semaine. Les mercredis et les week-ends ont les pics d'appels les plus élevés.**_

  	- Fluctuation mensuelle des appels abandonnés:
   ![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/e94c1aa68824c1552101557ab8c79890696b370d/src/graphes/line_month_abandoned.png)
	- _**Indique les variations mensuelles des appels abandonnés. On observe plus d'abandons pendant les mois avec beaucoup d'appels entrants.**_

	- Volume des appels abandonnés par jour:
 ![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/e94c1aa68824c1552101557ab8c79890696b370d/src/graphes/abandoned_calls_day.png)
	- _**Ce graphique nous montre la proportion des appels abandonnés par jour de la semaine. Les abandons sont plus fréquents les jours où le volume d'appels est important.**_

 	- Volume mensuel du temps d'attente:
  ![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/fa2759f665e0cf72e872b5b75f5490bfc777bba9/src/graphes/waiting_time_month%20(2).png)
  	- _**Cette visualisation indique combien de temps les clients attendent avant qu'un agent ne réponde. Les temps d'attente sont plus longs pendant les mois avec beaucoup d'appels.**_

  	- Saisonnalité de la qualité du service(c'est à dire le taux d'appels répondus en moins de 20 secondes):
   ![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/e94c1aa68824c1552101557ab8c79890696b370d/src/graphes/line_quality_rate.png)
	- _**Ce graphique indique que la qualité du service diminue pendant les périodes de forte affluence et qu'à contrario il augmente durant les périodes de faible affluence**_

 #### 3- Décryptage des relations: Corrélations entre les données du Centre d'Appels:
![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/978e55ab611eaa9a99dc5d4c3cdd2187bc740883/src/graphes/corr1.png)
	- _**Ce graphique illustre les relations entre les différentes métriques à l'aide d'un dégradé de couleurs, notons que plus la couleur est foncée plus la relation est forte et vice-versa.**_

---
## 5. **Insights(Observations) clés:**

Conformément aux visualisations et aux analyses effectuées, les observations suivantes ont émergées:

 ### 1- Périodes de rush ou de forte activité:
   - Au niveau des mois: Le mois de Décembre et le mois d'Octobre constituent des mois de forte activité avec un nombre total d'appels entrants qui dépasse la barre des 6400 pour ces deux mois.
   - Au niveau des jour de la semaine: Les appels entrants atteignent des pics le mercredi et le week-end, avec une activité relativement faible en début de semaine, notamment le mardi qui compte un nombre d'appels entrants anormalement bas.

 ### 2- Relation entre nos métriques:

   - Une corrélation parfaite entre les appels entrants(incoming_calls) et les appels répondus(answered_calls):
Ce qui montre que les agents ont une bonne réactivité et une bonne performance avec les fluctuations croissantes du nombre d'appels entrants, suggérant une capacité de réponse très constante quel que soit le volume des appels entrants.
	
   - Une corrélation négative très forte entre la vitesse de réponse et le service level, qui mesure le pourcentage d'appels répondus en moins de 20 secondes. Ce qui traduit que plus la réactivité de nos agents est bonne plus la qualité de leur service l'est également.

   - Une corrélation positive forte entre le nombre d'appels entrants et le nombre d'appels abandonnés: Ce qui signifie que plus les appels entrants augmentent plus le nombre d'appels abandonnés tend à augmenter également et inversement.

  - Une forte corrélation positive entre le temps d'attente et le nombre d'appels abandonnés: ce qui induit que le nombre d'appels abandonnés tend à augmenter avec la hausse du temps d'attente moyen et inversement.
	

 ### 3- Durée des appels:
   - La durée des appels est assez constante quelque soit le niveau d'affluence, ce qui traduit une adaptabilité moindre de nos agents selon que la période soit calme ou à forte activité.


 ### 4- Impact des périodes de rush sur les ratios ou indicateurs de performance:
   - Service Level rate: Les mois avec une forte affluence tels que Décembre et Octobre ont des taux d'appels répondus en moins de 20 secondes(service_level_rate) autour de 61 et 71 % alors que d'autres mois avec moins d'activité tels que Juin, Mars et Avril ont un service level rate plus élevé, cela montre une corrélation entre le nombre d'appels entrants et le service level rate qui rappelons le, représente le nombre d'appels qui ont reçu une réponse en moins de 20 secondes.


 ### 5- Distribution des variables numériques:
   - La distribution des appels entrants: Cette distribution est notamment asymétrique à droite avec une majorité des appels entre 100 et 200, avec quelques valeurs atypiques entre 350 et 800 appels journalier. Cela signifie que la majorité des jours ont un nombre d'appels plutôt modéré avec de rares jours avec des pics d'activités.

   - La distribution des appels abandonnés: Cette distribution est asymétrique à droite avec une concentration des appels abandonnés entre 0 et 20 ce qui indique que les abandons sont limités. Cette asymétrie montre également des cas où le nombre d'abandon est plus élevé, mais ces cas restent des exceptions.

   - La distribution de la vitesse de réponse: Cette distribution est également asymétrique à droite avec une concentration entre 10 et 25 secondes environ, signe d'une performance relativement bonne de nos agents. Cette asymétrie montre néanmoins des vitesse de réponse dépassant les 40 secondes, mais ces cas restent des exceptions qui ont notamment lieu lors des périodes de forte affluence, même s' il reste à noter que mardi qui reste un jour calme, d'ailleurs le plus calme de la semaine, a des vitesses de réponse qui sont en contradiction totale avec le flux d'appels de ce jour, cela suggère que le mardi le nombre d'agents est réduit de manière exagéré, ce qui entraîne de mauvaises performances.

   - La distribution de la durée des appels: Cette dernière est leptokurtique, c'est à dire avec une pointicité prononcée, ce qui indique une forte concentration de la durée des appels autour de la moyenne. Cela signifie que la durée des appels est relativement similaire, là en l' occurrence elle se situe entre 100 et 150 secondes, ce qui est  signe d'une bonne efficacité de nos agents. Notons que les valeurs atypiques c'est à dire les durée supérieures à 160 secondes se concentrent les jours de faibles activité, notamment le lundi et le mardi.

   - La distribution du temps d'attente: On observe là une asymétrie positive, ce qui indique une concentration du temps d'attente entre 100 et 200 secondes, avec une floppée de valeurs anormales au delà de 400 secondes ce qui indique que certains clients doivent attendre trop longtemps avant d'être pris en charge par nos agents. Cela a notamment lieu lors des périodes de rush indiquant une mauvaise optimisation des ressources lors de ces périodes. Notons qu'à contrario lors des périodes calmes, c'est à dire le lundi et le mardi le temps d'attente est relativement bas, cela illustre là encore la forte relation entre l'affluence de notre centre d'appels et la performance globale de nos agents.


## 6. **Recommandations:**
Les suivantes recommandations basées sur les insights qui découlent de mon analyse aideront la société à accroître sa performance de façon optimum en donnant des précisions fiables sur les périodes de rush:

#### 1- Prévoir une augmentation d'effectif durant les mois de Décembre et d' Octobre:
Du fait d'une augmentation exponentielle du nombre d'appels entrants il est impératif de solliciter plus d'agents pour faire face à ces périodes de rush et ainsi assurer un service de qualité aux appelants.

#### 2- Procéder à une optimisation des ressources pendant les périodes calmes:
Réaliser un ajustement dynamique des équipes pour mieux allouer les ressources pendant les jours de la semaine calme, c'est à dire le mardi et le lundi, ce qui pourrait réduire les coûts ou permettre de réorienter les agents vers d'autres tâches.


#### 3- Automatisation des Appels pour les demandes simples et récurrentes:
Envisager d'implémenter un système de réponse vocale interactif ou un chatbot pour les demandes redondantes et simples, permettant ainsi de libérer nos agents pour les appels les plus complexes et d'augmenter la vitesse de réponse en réduisant bien évidemment le temps d'attente; tout ça pour améliorer encore plus la qualité des services de notre centre d'appels.


#### 4- Améliorer la formation des agents pour les périodes de rush:
Former les agents à des techniques de gestion des appels rapides pour les périodes d'affluence tout en préservant la qualité du service. Cela permettra notamment de réduire drastiquement le temps d'attente et ainsi le nombre d'appels abandonnés par nos clients.


#### 5- Prévoir des messages informatifs pour les clients en file d'attente:
Des messages informatifs de la position en file d'attente pourraient notamment diminuer la frustration lors de périodes d'attente relativement longues et ainsi dissuader les clients d'abandonner l'appel.


#### 6- Former les agents pour une résolution rapide des besoins des clients:
Une telle mesure pourrait permettre une meilleur gestion des ressources durant les périodes de rush et ainsi entraîner un nombre d'appels abandonnés le plus bas possible durant ces périodes de forte activité.
