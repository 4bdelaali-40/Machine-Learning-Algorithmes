# Classification Iris avec k-Nearest Neighbors (k-NN)

Ce dépôt illustre pas à pas l'implémentation d'un modèle de classification **k-NN** sur le célèbre dataset **Iris**. Vous y trouverez :

- Exploration et visualisation du jeu de données
- Préparation train/test
- Entraînement et évaluation du modèle
- Interface interactive avec `ipywidgets`

---

## En console (Pour tester le fonctionement de modele avec une nouvelle donnees)

```python
sepal_length = float(input("Longueur du sépale (cm) : "))
sepal_width  = float(input("Largeur du sépale (cm) : "))
petal_length = float(input("Longueur du pétale (cm) : "))
petal_width  = float(input("Largeur du pétale (cm) : "))

features = [[sepal_length, sepal_width, petal_length, petal_width]]
pred = knn.predict(features)[0]
print("Espèce prédite :", iris.target_names[pred])
```

---

## Résultats attendus
- **Précision** : généralement ≥ 0.97 sur le dataset Iris
- **Rapport de classification** détaillé (précision, rappel, f1-score)
- **Matrice de confusion** affichée avec seaborn

## À propos du dataset Iris

Le dataset Iris contient 150 observations de fleurs, réparties en 3 espèces : *Iris setosa*, *Iris versicolor*, *Iris virginica*. Chaque échantillon est décrit par 4 caractéristiques :
- Longueur et largeur du sépale
- Longueur et largeur du pétale