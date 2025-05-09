# Projet Clustering DBSCAN sur Données Retail (RFM)

## Description

Ce projet réalise un clustering non supervisé des clients d'un dataset retail (transactions) à l'aide de l'algorithme **DBSCAN**. Il s'appuie sur une approche **RFM** (Recency, Frequency, Monetary) pour caractériser chaque client avant de segmenter.

### Étapes principales

1. **Chargement et préparation**

   * Lecture du fichier CSV (`retail.csv`) contenant les colonnes : `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`.
2. **Feature Engineering – RFM**

   * Filtrage des transactions positives
   * Calcul de `Recency` (jours depuis dernière transaction), `Frequency` (nombre de factures), `Monetary` (montant total dépensé)
3. **Nettoyage**

   * Imputation des valeurs manquantes (médiane)
   * Traitement des outliers (clipping aux percentiles 1 et 99)
4. **Transformation & Normalisation**

   * Réduction de la skewness via `PowerTransformer` (Yeo-Johnson)
   * Standardisation (`StandardScaler`)
5. **DBSCAN**

   * Estimation visuelle de l’hyperparamètre `eps` (kNN-distance plot)
   * Exécution de `DBSCAN` avec `eps` et `min_samples`
6. **Évaluation**

   * Silhouette Score, Calinski-Harabasz, Davies-Bouldin (excluant le bruit)
7. **Visualisation**

   * Projection 2D des clusters via `PCA`
   * Histogramme des tailles de clusters
8. **Analyse**

   * Moyennes RFM par cluster
9. **Perspectives**

   * Affiner `eps` et `min_samples` via grid search
   * Explorer d’autres approches (HDBSCAN, GMM)
   * Intégration dans un pipeline de recommandation ou CRM

## Structure des fichiers

* `Clustering_DBSCAN.ipynb` : script Python complet et modulaire.
* `data.csv` : données de transactions.
* `README.md`

## Prérequis

* Python 3.8+
* Packages :

  * `pandas`, `numpy`, `matplotlib`
  * `scikit-learn`

Installation rapide :

```bash
pip install pandas numpy matplotlib scikit-learn
```

## Ajustement des hyperparamètres

* **`eps`** : distance maximale entre points pour être considérés comme voisins.

  * Estimable via le graphique des distances kNN (k = `min_samples`).
* **`min_samples`** : nombre minimal de points dans une sphère de rayon `eps` pour qu’un point soit noyau.

Pour trouver la meilleure combinaison, exécutez une recherche paramétrique (grid search) en enregistrant le **Silhouette Score** pour chaque couple (`eps`, `min_samples`).
