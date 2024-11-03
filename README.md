# Documentation Technique - Call Center Project

---

## Structure du Répertoire

Le projet est structuré comme suit :

- **README.md** : Ce fichier fournit une vue d'ensemble sur la structure du repo et sur la documentation technique du projet.
- **src/** : Ce dossier contient le code source, les datasets et les fichiers liés à l'analyse.
  - **data/** : Ce sous-dossier contient le fichier de données.
  - **cleaning.ipynb** : Contient le notebook Jupyter du nettoyage et du prétraitement des données.
  - **call_insights.ipynb**: Contient le notebook de l'analyse exploratoire des données.
  - **Reporting** : Contient les rapports générés à partir des analyses.

---

## 1. Introduction
Ce document décrit en détail le processus de nettoyage et de prétraitement des données utilisées dans le projet d'analyse des données du Call center. Il couvre les étapes de chargement, de nettoyage, de transformation, d'exploration, d'analyse ainsi que les techniques utilisées pour préparer les données pour l'analyse.

## 2 - Chargement et inspection des données:
#### 2-1 Les données ont été chargées à partir d'un fichier csv contenant les données d'un call center fictif durant l'année 2021 .

#### 2-2 Le jeu de données contient 365 lignes et 9 colonnes. Notons que les données du call center ont été agrégé pour chaque jour de l'année 2021, c'est ce qui explique la présence de 365 lignes.

#### 2-3 Les colonnes clés incluent toutes les colonnes présentes dans l'ensemble de donnée, soit: `Incoming Calls`, `Answered Calls`, `Abandoned Calls`, `Answer Rate`,  `Answer Speed(AVG)`, `Talk Duration(AVG)`, `Waiting Time(AVG)` et enfin `Service Level(20 seconds)`.



## 3 - Nettoyage des données:
#### 3-1 Vérification de la structure du dataframe et du type de donnée associé à nos variables.

#### 3-2 Renommage de nos colonnes conformément à la snake case convention.

#### 3-3 Recherche de valeurs manquantes et de lignes dupliquées.

#### 3-4 Conversion des types de données:
- La colonne date a été convertie en objet datetime.
- Les colonnes `talk_duration`, `waiting_time`, `answer_speed` ont été converties en objet de type entier(int) pour faciliter leur manipulation.
- On a procédé à la suppression du symbole qui représente les pourcentages dans les colonnes de taux(answer rate et service level(20 seconds)) et ensuite à leur conversion en objet de type décimale ou nombre flottants(float).
- Les colonnes `talk_duration`, `waiting_time`, `answer_speed` ont été encore renommées.
- Une conversion des données de int64 à int32 a été opérée dans un souci d'optimisation.
- La colonne `day_of_week` a également été convertie en objet category dans un souci d'optimisation.



## 4- Ingénierie des caractéristiques(nouvelles colonnes):
#### 4-1 Création d'une colonne `day_of_week` qui contient le nom des jours de la semaine correspondant aux dates.
#### 4-2 Extraction du nom du mois: une colonne `month` a été créée pour stocker le nom du mois correspondant a chaque date.



## 5- Vérification de l'uniformité des dates dans notre colonne date

## 6- Analyse statistique des données numériques:
#### 6-1 Analyse des indicateurs statistiques, notamment ceux de tendance centrale et ceux de dispersion pour nos variables quantitatives.

#### 6-2 Création de boxplots(boîte à moustache) pour analyser la distribution de quelques colonnes et notamment pour vérifier la présence d'outliers.
- J'ai opté pour une préservation des "outliers ou données aberrantes" pour le bien de l'analyse !


## 7- Finalisation et vérification de la qualité du nettoyage:
#### 7-1 On a une fois de plus procédé à une inspection de valeurs manquantes et de lignes dupliquées.
#### 7-2 On a également procédé à une vérification de nos données catégorielles, notamment le nombre de valeurs uniques.
#### 7-3 Une nouvelle inspection du type de colonnes a été effectuée.
#### 7-4 Enfin une vérification du format de nos dates dans la colonne date pour s'assurer de leur adéquation avec le format ISO 8601.


## 8 - Données nettoyées finales:
Après toutes les étapes précitées notre jeu de données est normalisé et exploitable pour les analyses. Eu égard à tout ce qui a précédé, nous avons:
#### 8-1 Lignes supprimées: Aucune ligne n'a été supprimée.
#### 8-2 Nouvelles colonnes: Nous avons deux nouvelles colonnes: day et month pour nous faciliter une analyse de nos données suivant divers niveaux de granularité !

---

## Plan d'Analyse Exploratoire:
Dans cette partie je documente la phase d'analyse de mes données.

### 1- Analyse Descriptive générale:
Ici j'ai commencé à obtenir une vue d'ensemble des données pour identifier les caractéristiques clés, les indicateurs qui synthétisent le mieux la structure de mes données avant de rentrer dans les détails.

### 2- Visualisation de la distribution de mes variables statistiques:
Cette étape m'a permis de comprendre la dispersion, la symétrie, l'aplatissement de mes données et la détection des valeurs les plus marginales à l'aide d'histogrammes, un graphique qui permet notamment d'appréhender la distribution d'une variable continue.

### 3- Agrégation de mes données par périodes:
Là mon objectif était de transformer les données en segments temporels(par jour de la semaine, par mois), de les rééchantillonner selon divers niveau de granularité, tout ça dans le but d'identifier des tendances comme les périodes de rush.


### 4- Analyse des tendances et saisonnalité:
Cette phase post agrégation a vu l'analyse et l'exploration de mes données pour identifier les tendances récurrentes dans nos données. Elle a vu la création de graphique de ligne et de graphiques en barre pour explorer nos données agrégées et faire ainsi émerger des insights et des tendances notoires.


### 5- Corrélation entre variables:
Dans cette phase j'ai entreprit de voir s'il y'avait des relations entre les différentes métriques de mon ensemble de données, pour révéler des facteurs d'influences entre elles. J'ai notamment utilisé durant cette phase des nuages de points et une matrice de corrélation.


### 6- Analyse des Performances et Identification des périodes de rush:
Cette partie a eu pour but: de détecter les périodes de rush et évaluer la performance globale du centre d'appels.

