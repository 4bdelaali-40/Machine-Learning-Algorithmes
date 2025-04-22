# Prédiction de prix de maisons avec Régression Linéaire

## Objectif
Ce projet vise à construire un modèle de régression linéaire pour prédire le prix d'une maison en fonction de plusieurs caractéristiques :
- Revenu moyen de la zone
- Âge moyen des maisons
- Nombre moyen de pièces
- Nombre moyen de chambres
- Population de la zone

---

##  Etapes du projet

### 1. Chargement et exploration des données
- Charger le fichier `USA_Housing.csv` dans un DataFrame avec pandas
- Afficher les premières lignes pour avoir un aperçu des données
- Utiliser `.info()` et `.describe()` pour comprendre les types et statistiques
- Générer une matrice de corrélation avec seaborn pour visualiser les liens entre les variables

### 2. Préparation des données
- Sélectionner les features (X) et la variable cible (y)
- Diviser les données en sets d'entraînement et de test avec `train_test_split`

### 3. Entraînement du modèle
- Utiliser `LinearRegression()` de `sklearn.linear_model`
- Entraîner le modèle sur les données d'entraînement

### 4. Évaluation du modèle
- Prédire les valeurs sur l'ensemble de test
- Calculer :
  - Mean Absolute Error (MAE)
  - Root Mean Squared Error (RMSE)
  - R2 Score

### 5. Prédiction interactive avec ipywidgets
- Créer des champs de saisie (`FloatText`) pour entrer les caractéristiques d'une maison
- Ajouter un bouton "Predict"
- Afficher la prédiction dans la cellule quand l'utilisateur clique sur le bouton


## 📁 Structure du projet
```
regression_lineaire/
├── USA_Housing.csv       # Dataset initial
├── app.ipynb        # Notebook Jupyter complet
├── README.md             # Ce fichier
```

Dataset

Source : Kaggle - USA Housing Dataset