# Projet de Classification : Régression Logistique Interactif

## Description
Ce projet implémente un pipeline complet de classification binaire à l'aide de la régression logistique sur le dataset "Breast Cancer" de scikit-learn. Il combine :

1. **Exploration des données (EDA)** :
   - Aperçu du DataFrame
   - Statistiques descriptives et infos générales
   - Visualisations (distribution de la cible, histogrammes, boxplots, heatmap de corrélation)

2. **Prétraitement et entraînement** :
   - Séparation en jeu d'entraînement et de test
   - Standardisation (StandardScaler)
   - Entraînement d'un modèle `LogisticRegression` avec régularisation

3. **Évaluation** :
   - Mesures de performance (accuracy, classification report, matrice de confusion)
   - Courbe ROC / AUC

4. **Interface interactive** :
   - Widgets `ipywidgets` pour saisir dynamiquement les 30 caractéristiques
   - Affichage en temps réel de la prédiction (Bénigne / Maligne) et de la probabilité associée

## Structure des fichiers

- `reg_logistique.py` : script principal exécutant le modèle et l'interface interactive.
- `README.md` : documentation du projet.

## Prérequis

- Python 3.8+
- Packages Python :
  - `pandas`
  - `scikit-learn`
  - `matplotlib`
  - `ipywidgets`
  - `jupyterlab` (ou `notebook`)

Installez-les via :

```bash
pip install pandas scikit-learn matplotlib ipywidgets jupyterlab
jupyter nbextension enable --py widgetsnbextension
```

## Utilisation

1. Ouvrez un terminal et lancez Jupyter Lab/Notebook :
   ```bash
   jupyter lab
   ```
2. Chargez le fichier `predict_logistic_interactif.py` dans un notebook Python.
3. Exécutez la cellule pour afficher l'interface interactive.
4. Ajustez les curseurs pour chaque feature et cliquez sur **Prédire**.
5. Consultez la prédiction et la probabilité.

## Personnalisation

- **EDA** : modifiez les visualisations dans une cellule séparée pour explorer d'autres graphiques (pairplot, PCA, etc.).
- **Hyperparamètres** : ajustez `max_iter` ou le paramètre `C` de `LogisticRegression`.
- **Seuil de décision** : changez le seuil par défaut (0.5) pour privilégier recall ou precision.

## Interprétation des résultats

- Les coefficients du modèle reflètent l'impact de chaque variable sur le log-odds de la classe "Maligne".
- La courbe ROC et la valeur AUC quantifient la capacité du modèle à séparer les deux classes.

---