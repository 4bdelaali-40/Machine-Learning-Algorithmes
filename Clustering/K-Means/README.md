# Projet de Segmentation Clients par K-means

## Description du projet
Ce projet implémente une analyse de segmentation clients à l'aide de l'algorithme K-means sur un dataset de comportements de titulaires de cartes de crédit. L'objectif est d'identifier des segments de clients distincts en fonction de leurs habitudes d'achat, de paiement et d'utilisation du crédit, afin de développer des stratégies marketing personnalisées.

## Dataset
Le dataset utilisé contient des informations sur les comportements des clients de cartes de crédit avec les variables suivantes :

| Variable | Description |
|----------|-------------|
| CUST_ID | Identifiant unique du client |
| BALANCE | Solde du compte |
| BALANCE_FREQUENCY | Fréquence de mise à jour du solde (score entre 0 et 1) |
| PURCHASES | Total des achats |
| ONEOFF_PURCHASES | Achats ponctuels |
| INSTALLMENTS_PURCHASES | Achats par versements |
| CASH_ADVANCE | Avances de fonds |
| PURCHASES_FREQUENCY | Fréquence des achats (score entre 0 et 1) |
| ONEOFF_PURCHASES_FREQUENCY | Fréquence des achats ponctuels (score entre 0 et 1) |
| PURCHASES_INSTALLMENTS_FREQUENCY | Fréquence des achats par versements (score entre 0 et 1) |
| CASH_ADVANCE_FREQUENCY | Fréquence des avances de fonds (score entre 0 et 1) |
| CASH_ADVANCE_TRX | Nombre de transactions d'avance de fonds |
| PURCHASES_TRX | Nombre de transactions d'achat |
| CREDIT_LIMIT | Limite de crédit |
| PAYMENTS | Total des paiements |
| MINIMUM_PAYMENTS | Total des paiements minimums |
| PRC_FULL_PAYMENT | Pourcentage de paiements complets |
| TENURE | Durée en tant que client (mois) |


## Prérequis
Pour exécuter ce projet, vous aurez besoin des bibliothèques Python suivantes :
```
pandas>=1.3.0
numpy>=1.20.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=0.24.0
```


## Méthodologie
Le projet suit les étapes suivantes :

1. **Chargement et exploration des données** : Importation du dataset, analyse statistique descriptive et détection des valeurs manquantes.

2. **Prétraitement des données** : Gestion des valeurs manquantes, normalisation des variables.

3. **Détermination du nombre optimal de clusters** : Utilisation de la méthode du coude et du score silhouette pour identifier le nombre optimal de clusters (k=3 selon les résultats).

4. **Application de l'algorithme K-means** : Segmentation des clients avec k=3.

5. **Visualisation des clusters** : Représentation graphique des segments à l'aide de PCA, heatmaps et graphiques radar.

6. **Analyse et interprétation** : Caractérisation des segments identifiés et formulation de recommandations marketing.

## Résultats principaux
Le projet a permis d'identifier 3 segments distincts de clients :

1. **Les utilisateurs occasionnels** : Faible utilisation de la carte, peu d'achats, solde généralement bas.

2. **Les gros acheteurs** : Volume d'achats élevé, paiements réguliers et importants, utilisation fréquente de la carte.

3. **Les utilisateurs d'avances de fonds / crédit** : Utilisation fréquente des avances de fonds, solde élevé, paiements minimums fréquents.

Pour chaque segment, des recommandations marketing spécifiques sont proposées dans le rapport d'analyse.

## Personnalisation
Vous pouvez ajuster certains paramètres du script pour personnaliser l'analyse :

- Modifier le nombre de clusters (variable `optimal_k`).
- Adapter les variables utilisées pour l'analyse (liste `key_features`).
- Modifier les interprétations des profils en fonction de vos connaissances du domaine.

