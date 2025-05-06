# Projet SVM Interactif sur le dataset Iris

## Description

Ce projet implémente un pipeline complet de classification multiclasses à l'aide d'un **SVM (Support Vector Machine)** sur le dataset **Iris** de scikit-learn. Il propose :

1. **Chargement et exploration des données** (EDA) : aperçu, statistiques descriptives, distribution des classes, histogrammes et heatmap de corrélation.
2. **Prétraitement** : standardisation des features.
3. **Entraînement** : SVM à noyau RBF (`kernel='rbf'`) avec probabilités (`probability=True`).
4. **Interface interactive** via `ipywidgets` : sliders dynamiques pour chaque feature, bouton de prédiction et affichage des probabilités pour chaque classe.

## Structure des fichiers

* `svm_algorithmef.ipynb` : notebook principal intégrant le code d’entraînement et l’interface interactive.
* `README.md` : documentation du projet.

## Prérequis

* Librairies Python :

  * `pandas`
  * `scikit-learn`
  * `matplotlib`
  * `ipywidgets`
  * `jupyterlab` ou `notebook`

Installez-les avec :

```bash
pip install pandas scikit-learn matplotlib ipywidgets jupyterlab
jupyter nbextension enable --py widgetsnbextension
```

## Utilisation

1. Lancez Jupyter Lab ou Notebook dans votre environnement :

   ```bash
   jupyter lab
   ```
2. Ouvrez `svm_interactif.ipynb`.
3. Exécutez la cellule d’entraînement :

   ```python
   from sklearn.datasets import load_iris
   from sklearn.model_selection import train_test_split
   from sklearn.preprocessing import StandardScaler
   from sklearn.svm import SVC

   iris = load_iris(as_frame=True)
   df = iris.frame
   X = df.drop(columns=[iris.target.name])
   y = df[iris.target.name]

   scaler = StandardScaler().fit(X)
   model = SVC(kernel='rbf', probability=True, C=1.0, gamma='scale')
   model.fit(scaler.transform(X), y)
   ```
4. Exécutez la cellule interactive ci-dessous pour afficher les sliders et le bouton de prédiction.
5. Ajustez les curseurs pour chaque feature et cliquez sur **Prédire (SVM)** pour voir :

   * La classe prédite (`setosa`, `versicolor`, `virginica`).
   * Les probabilités associées à chaque classe.

## Personnalisation

* **Kernel & Hyperparamètres** : modifiez `kernel`, `C` ou `gamma` dans l’instanciation de `SVC`.
* **Apparence** : ajustez la taille et le style des widgets avec les options `layout`.
* **Dataset** : remplacez `load_iris()` par un autre dataset de scikit-learn (Wine, Digits…) et adaptez la liste `iris.target_names`.

## Perspectives d’évolution

* Ajouter une section d’EDA plus poussée (pairplot, PCA interactive).
* Intégrer une recherche d’hyperparamètres en temps réel dans le notebook.
* Proposer une version web (Dash ou Streamlit) pour déployer l’interface.

