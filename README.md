# B2B E-Commerce & Wholesale BI

## Présentation du projet

Ce projet porte sur le pilotage stratégique d'une centrale d'achat B2B à travers l'analyse des commandes de gros, des entreprises clientes et des fournisseurs.

L'objectif est de construire une solution de Business Intelligence permettant d'analyser les volumes de commandes, le chiffre d'affaires et la performance selon la segmentation des entreprises clientes.

## Problématique

Comment piloter efficacement les volumes de commandes de gros et sécuriser la croissance du chiffre d'affaires en fonction de la segmentation des entreprises clientes ?

## Objectifs

- Analyser le chiffre d'affaires global.
- Suivre les volumes de produits commandés.
- Analyser les performances par catégorie d'entreprise.
- Étudier l'évolution des ventes dans le temps.
- Permettre une analyse interactive des données.
- Faciliter l'identification des zones de croissance et de sous-performance.

## Architecture des données

Le grain d'analyse choisi est la transaction unitaire, correspondant à une facture.

Le modèle repose sur une architecture en étoile (Star Schema) composée d'une table de faits et de dimensions d'analyse.

### Table de faits

`Fichiers_Faits_B2B`

Principales mesures :

- `Montant_Facture`
- `Quantite_Gros`
- Chiffre d'affaires global
- Volume total
- Panier moyen

### Dimensions

#### Dimension Entreprise

- `ID_Entreprise`
- `NOM_ENTREPRISE`
- `Categorie`

#### Dimension Temps

- `Date`

La relation entre la dimension Entreprise et la table de faits est de type 1:N.

## Pipeline ETL

Le projet utilise Power Query pour préparer et transformer les données avant leur analyse dans Power BI.

### Transformations réalisées

- Conversion des montants en nombres décimaux.
- Gestion des séparateurs numériques avec les paramètres régionaux.
- Suppression des doublons dans la dimension Entreprise.
- Vérification de l'intégrité référentielle.
- Conversion et typage des dates.
- Préparation des données pour les analyses temporelles.

## Modèle de données

Le modèle en étoile permet de simplifier la navigation dans les données et d'améliorer les performances des analyses interactives.

Cette architecture facilite notamment les filtres par :

- entreprise ;
- catégorie ;
- date ;
- période ;
- transactions.

## Mesures DAX

### Chiffre d'affaires global

```DAX
CA Global = SUM(Fichiers_Faits_B2B[Montant_Facture])
```

Cette mesure permet de consolider l'ensemble des ventes.

### Volume total

```DAX
Volume total = SUM(Fichiers_Faits_B2B[Quantite_Gros])
```

Cette mesure permet de suivre le volume total des unités commandées.

### Panier moyen

```DAX
Panier Moyen = [CA Global] / [Volume total]
```

Cette mesure permet d'analyser la valeur moyenne générée par unité vendue.

## Dashboard Power BI

Le dashboard permet d'explorer les performances commerciales à travers des indicateurs et des filtres interactifs.

Les analyses portent notamment sur :

- le chiffre d'affaires ;
- les volumes de commandes ;
- les catégories d'entreprises ;
- l'évolution temporelle ;
- les zones de croissance ;
- les zones de sous-performance.

## Résultats

Le tableau de bord indique un chiffre d'affaires total de **12,50 millions**.

L'analyse sectorielle montre que la **Catégorie 2** constitue le principal moteur de l'activité.

L'interactivité du dashboard permet au décideur de filtrer les résultats par date ou par secteur afin d'identifier les performances et les zones nécessitant une attention particulière.

## Technologies utilisées

- Power BI
- Power Query
- DAX
- Business Intelligence
- Data Analysis
- Data Visualization
- ETL
- Star Schema

## Compétences mobilisées

- Conception d'un modèle dimensionnel.
- Modélisation en étoile.
- Préparation et transformation des données.
- Création de mesures DAX.
- Analyse décisionnelle.
- Création de dashboards interactifs.
- Data Visualization.
- Interprétation des indicateurs commerciaux.

## Auteur

Khadija Belbaraka

Data & AI | Data Analysis | Power BI | SQL | Python | Machine Learning
