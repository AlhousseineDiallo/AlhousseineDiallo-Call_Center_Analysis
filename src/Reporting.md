# Rapport d'Analyse - Call Center Project

## 1. Introduction:
Dans le cadre de l'analyse de données d'un centre d'Appels, nous avons entreprit une exploration et une analyse minutieuse des métriques dans le but de détecter les périodes de rush ou de forte activités du Centre d'Appels et les facteurs qui influencent le nombre d'appels abandonnés pour optimiser les performance du Centre d'Appels.

## Objectif du rapport:

L'analyse vise à répondre aux questions suivantes:
  - Quelles sont les périodes de rush ou de forte affluence ?
  - Comment optimiser les services du Centre d'Appels pour améliorer la satisfaction de nos clients ?
  - Quels sont les facteurs qui influencent le nombre d'appels abandonnés ?

## Aperçu des données utilisées:

L'analyse est basé sur des données d'un centre d'appels fictif qui couvre l'année 2021.
Les principales métriques, qui ont constituées le socle, la pierre angulaire de mes analyses sont:

- `incoming_calls`: le nombre d'appels entrants, soit tous les appels que le centre d'appels a reçus.

- `answered_calls`: le nombre d'appels qui ont été répondus par nos agents.

- `abandoned_calls`: le nombre d'appels où l'appelant à raccroché avant de parler à un agent.

- `answer_speed(seconds)`: Le temps moyen en secondes que les agents ont mis pour répondre aux appels après que ces derniers aient été reçu.

- `waiting_time(seconds)`: Le temps moyen en secondes que les appelants ont passé en attente avant qu'un agent ne réponde.

- `talk_duration(seconds)`: Le temps moyen en secondes des conversations entre les agents et les appelants.

---

## **Visualisation des tendances et des performances: Analyse Graphiques**
### Introduction:

Dans cette section, nous explorons les données du centre d'appels à travers des visualisations graphiques afin de mettre en évidence les tendances, les distributions et les relations entre les différentes métriques clés. Les graphiques permettent une compréhension visuelle des comportements observés, comme les périodes de forte activité, les variations de performance en fonction des jours ou des mois, et les éventuelles corrélations entre variables.

### Graphiques de distribution des variables clés:
 #### 1- Histogrammes pour les variables continues:
	- Ditribution des appels entrants:
![**Distribution des appels entrants**](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/3a79ce3eb0af52812e4f9ab45c8fa92303f4cad0/src/graphes/incoming_calls_dist.png)

	- Distribution des appels abandonnés:
 ![**Distribution des appels abandonnés**](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/3165ef2fe2985f1ed97070853da0b57124a717e2/src/graphes/abandoned_dist.png)

	- Distribution de la vitesse de réponse:
 ![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/3165ef2fe2985f1ed97070853da0b57124a717e2/src/graphes/answer_time_dist.png)

#### 2- Segmentation des variables clés temporellement(par mois et par jour):
	- Volume des appels entrants par mois:
 ![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/7bfce6d3183c993075b697cd79f2ddfffb1aa2d8/src/graphes/incoming_calls_month.png)

 	- Volume des appels entrants par jour:
  ![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/695425f471cb3094a2b3d792be4eab78a599b2fe/src/graphes/incoming_calls_day.png)


  	- Fluctuation mensuelle des appels abandonnés:
   ![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/e94c1aa68824c1552101557ab8c79890696b370d/src/graphes/line_month_abandoned.png)


	- Volume des appels abandonnés par jour:
 ![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/e94c1aa68824c1552101557ab8c79890696b370d/src/graphes/abandoned_calls_day.png)

 	- Variation mensuelle du temps d'attente:
  ![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/e94c1aa68824c1552101557ab8c79890696b370d/src/graphes/waiting_time_month.png)

  	- Saisonnalité de la qualité du service(C'est à dire le taux d'appels répondus en moins de 20 secondes):
   ![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/e94c1aa68824c1552101557ab8c79890696b370d/src/graphes/line_quality_rate.png)

#### 3- Décryptage des relations: Corrélations entre les données du Centre d'Appels:
![](https://github.com/AlhousseineDiallo/AlhousseineDiallo-Call_Center_Analysis/blob/978e55ab611eaa9a99dc5d4c3cdd2187bc740883/src/graphes/corr1.png)
   
---
## **Insights(Observations) clés:**

Conformément aux visualisations et aux analyses effectuées, les observations suivantes ont émergées:

### 1- Périodes de rush ou de forte activité:
  - Au niveau des mois: Le mois de Décembre et le mois d'Octobre constituent des mois de forte activité avec un nombre total d'appels entrants qui dépasse la barre des 6400 pour ces deux mois.
  - Au niveau des jour de la semaine: Les appels entrants atteignent des pics le mercredi et le week-end, avec une activité relativement faible en début de semaine notamment le mardi qui compte un nombre d'appels entrants anormalement bas.

### 2- Relation entre nos métriques:

  - Une corrélation parfaite entre les appels entrants(incoming_calls) et les appels répondus(answered_calls):
Ce qui montre que les agents montrent une bonne réactivité et une bonne performance avec les fluctuations croissantes du nombre d'appels entrants, suggérant une capacité de réponse très constante quel que soit le volume des appels entrants.
	
  - Une corrélation négative très forte entre la vitesse de réponse et le service level qui mesure le pourcentage d'appels répondus en moins de 20 secondes. Ce qui traduit que plus la réactivité de nos agents est bonne plus la qualité de leur service l'est également.

  - Une corrélation positive forte entre le nombre d'appels entrants et le nombre d'appels abandonnés: Ce qui traduit que plus les appels entrants augmentent plus le nombre d'appels abandonné tend à augmenter également et inversement.

  - Une forte corrélation positive entre le temps d'attente et le nombre d'appels abandonnés: ce qui induit que le nombre d'appels abandonnés tend à augmenter avec la hausse du temps d'attente moyen et inversement.
	

### 3- Durée des appels:
  - La durée des appels est assez constante quelque soit le taux d'affluence, ce qui traduit une adaptabilité moindre de nos agents selon que la période soit calme ou à forte activité.


### 4- Impact des périodes de rush sur les ratios ou indicateurs de performance:
  - Service Level rate: Les mois avec une forte affluence tels que Décembre et Octobre ont des taux d'appels répondus en moins de 20 secondes(service_level_rate) autour de 61 et 71 % alors que d'autres mois avec moins d'appels tels que Juin, Mars et Avril ont des taux d'appels répondus en moins de 20 secondes plus grand.


### 5- Distribution des variables numériques:
  - La distribution des appels entrants: Cette distribution est notamment asymétrique à droite avec une majorité des appels entre 100 et 200, avec quelques valeurs atypiques entre 350 et 800 appels journalier. Cela signifie que la majorité des jours ont un nombre d'appels plutôt modéré avec de rare jour avec des pics d'activités.

  - La distribution des appels abandonnés: Cette distribution est asymétrique à droite avec une concentration des appels abandonnés entre 0 et 20 ce qui indique que les abandons sont limités. Cette asymétrie montre également des cas où le nombre d'abandon est plus élevé, mais ces cas restent des exceptions.

  - La distribution de la vitesse de réponse: Cette distribution est également asymétrique à droite avec une concentration entre 10 et environ 25 secondes signe d'une performance relativement bonne de nos agents. Cette asymétrie montre néanmoins des vitesse de réponse dépassant les 40 secondes, mais ces cas restent des exceptions qui ont notamment lieu lors des périodes de forte affluence, même si il reste à noter que mardi qui reste un jour calme, d'ailleurs le plus calme de la semaine à des vitesses de réponse qui sont en antinomie totale avec le flux d'appels pour ce jour, cela suggère que le mardi le nombre d'agents est réduit de manière exagéré, ce qui entraîne de mauvaises performances pour ce jour.

  - La distribution de la durée des appels: Cette dernière est leptokurtique, c'est à dire avec une pointicité prononcée, ce qui indique une forte concentration de la durée des appels autour de la moyenne. Cela signifie que la durée des appels est relativement similaire, là en l' occurrence elle se situe entre 100 et 150 secondes, ce qui est  signe d'une bonne efficacité de nos agents. Notons que les valeurs atypiques c'est à dire les durée supérieures à 160 secondes se concentrent les jours de faibles activité notamment le lundi et le mardi.

  - La distribution du temps d'attente: On observe là une asymétrie positive, ce qui indique une concentration des temps d'attente entre 100 et 200 secondes, avec une floppée de valeurs anormales au delà de 400 secondes ce qui indique que certains clients doivent attendre trop longtemps avant d'être pris en charge par nos agents. Cela a notamment lieu lors des périodes de rush indiquant une mauvaise optimisation des ressources lors de ces périodes. Notons qu'à contrario lors des périodes calmes, c'est à dire le lundi et le mardi le temps d'attente est relativement bas.


## - **Recommandations:**
Les suivantes recommandations basées sur les insights qui découlent de mon analyse aideront la société à accroître sa performance de façon optimum en donnant des précisions fiables sur les périodes de rush:

#### 1- Prévoir une augmentation d'effectif durant les mois de Décembre et d' Octobre:
Du fait d'une augmentation exponentielle du nombre d'appels entrants il est impératif de solliciter plus d'agents pour faire face à ces périodes de rush et ainsi assurer un service de qualité aux appelants.

#### 2- Procéder à une optimisation des ressources pendant les périodes calmes:
Réaliser un ajustement dynamique des équipes pour mieux allouer les ressources pendant les jours de la semaine calme, c'est à dire le mardi et le lundi, ce qui pourrait réduire les coûts ou permettre de réorienter les agents vers d'autres tâches.


#### 3- Automatisation des Appels pour les demandes simples et récurrentes:
Envisager d'implémenter un système de réponse vocale interactif ou un chatbot pour les demandes redondantes et simples, permettant ainsi de libérer nos agents pour les appels les plus complexes et d'augmenter la vitesse de réponse en réduisant bien évidemment le temps d'attente; tout ça pour améliorer encore plus la qualité des services de notre centre d'appels.


#### 4- Améliorer la formation des agents pour les périodes de rush:
Former les agents à des techniques de gestion des appels rapides pour les périodes d'affluence, tout en préservant la qualité du service. Cela permettra notamment de réduire drastiquement le temps d'attente et ainsi le nombre d'appels abandonnés par nos clients.


#### 5- Prévoir des messages informatif pour les clients en file d'attente:
Ces messages informatif de la position en file d'attente pourraient notamment diminuer la frustration lors de périodes d'attente relativement longues et ainsi dissuader les clients d'abandonner l'appel.


#### 6- Former les agents pour une résolution rapide des besoins des clients:
Une telle mesure pourrait permettre une meilleur gestion des ressources durant les périodes de rush et ainsi assurer un nombre d'appels abandonnés le plus bas possible durant ces périodes de forte activité.
