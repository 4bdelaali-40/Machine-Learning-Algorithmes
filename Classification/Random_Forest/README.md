# Projet de Classification Random Forest sur Digits

## Description

Ce projet met en place un pipeline complet de classification du dataset **Digits** (chiffres manuscrits 0–9) de `scikit-learn`, en utilisant un **RandomForestClassifier**. Le notebook/script propose :

1. **Exploration des données (EDA)**

   * Affichage des premières images et de leurs labels
   * Distribution des classes
   * Images moyennes par chiffre
   * Projection en 2D via PCA
   * Histogramme global des intensités de pixels

2. **Prétraitement**

   * Standardisation des 64 features (pixels) avec `StandardScaler`
   * Séparation en jeux d'entraînement et de test (70/30)

3. **Entraînement**

   * `RandomForestClassifier(n_estimators=100, random_state=42)`
   * Entraînement sur l’ensemble d’entraînement standardisé

4. **Évaluation**

   * Accuracy
   * Rapport de classification (precision, recall, f1-score)
   * Matrice de confusion

5. **Interface interactive**

   * Sélecteur d’index de l’échantillon de test avec `ipywidgets` (slider)
   * Affichage de l’image sélectionnée, du label réel, de la prédiction et des probabilités pour chaque classe

## Fichiers

* `random_forest.ipynb` : notebook principal contenant tout le code.
* `README.md` : documentation du projet.

## Prérequis

* Librairies Python :

  * `numpy`, `pandas`, `matplotlib`
  * `scikit-learn`
  * `ipywidgets` (pour l’interface interactive)
  * `jupyterlab` ou `notebook` (pour exécuter le notebook)

Installation rapide :

```bash
pip install numpy pandas matplotlib scikit-learn ipywidgets jupyterlab
jupyter nbextension enable --py widgetsnbextension
```

## Utilisation

1. Lancez Jupyter Lab ou Notebook :

   ```bash
   jupyter lab
   ```
2. Ouvrez `rf_digits_project.ipynb` ou exécutez `rf_digits_project.py`.
3. Exécutez les cellules d’**EDA**, de **prétraitement** et d’**entraînement** pour générer les visualisations et entraîner le modèle.
4. Lancez la cellule d’**interface interactive** : un **slider** apparaît pour sélectionner un échantillon de test.
5. Déplacez le curseur pour voir l’image, la prédiction, et les probabilités associées.

## Personnalisation

* **Hyperparamètres** : modifiez `n_estimators`, `max_depth`, etc., dans la création du `RandomForestClassifier`.
* **Visualisations** : ajoutez d’autres graphiques (t-SNE, heatmap des importances de features…).
* **Jeu de données** : remplacez `load_digits()` par un autre jeu (Iris, Wine, MNIST via `fetch_openml()`).

## Perspectives

* Analyse des **importances de variables** pour identifier les pixels les plus discriminants.
* Export du modèle via `joblib` et création d’une API (Flask/FastAPI) pour déployer la prédiction.
* Ajout d’une interface web légère (Streamlit) pour un usage non technique.
