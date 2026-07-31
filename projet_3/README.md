# 🚴 Projet 03 — Clustering & Algorithmes : Dessiner le Tour de France 2027

Ce projet consiste à construire un **tracé fictif du Tour de France 2027** à partir de 120 villages français.

L'objectif est de :

* 📍 Regrouper les villages en **21 étapes** avec du clustering.
* 📊 Comparer **K-Means** et **CAH** avec le score de silhouette et les tailles des groupes.
* 🌍 Calculer les distances géographiques avec la **formule de Haversine**.
* 🧭 Construire les parcours avec un **algorithme glouton**.
* 🔄 Améliorer les parcours avec l'algorithme **2-opt**.
* 🏁 Sélectionner le meilleur parcours pour chaque étape.

## 🛠️ Technologies

* Python
* Pandas
* Matplotlib
* Scikit-learn
* K-Means
* Clustering hiérarchique (CAH)
* Haversine
* Algorithme glouton
* 2-opt

## 📂 Fichiers

```text
Projet_03/
├── projet_03.ipynb
├── villages_2027.csv
└── utils.py
```

## 📊 Résultat

Le projet permet de passer d'un parcours naïf d'environ **46 789 km** à un tracé d'environ **4 000 km** réparti sur **21 étapes**.

Le parcours final est visualisé sur une carte et présenté sous forme de **livre de route**, avec les villages de départ et d'arrivée ainsi que la distance de chaque étape.

## 🎯 Ce que j'ai appris

* Utiliser le **clustering non supervisé**.
* Comparer plusieurs algorithmes de clustering.
* Interpréter un **score de silhouette**.
* Manipuler des coordonnées GPS.
* Calculer des distances avec la **formule de Haversine**.
* Comprendre le problème du **voyageur de commerce (TSP)**.
* Utiliser des **heuristiques d'optimisation** avec le glouton et le 2-opt.
* Combiner plusieurs algorithmes pour construire une solution plus efficace.
