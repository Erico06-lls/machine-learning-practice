# 🍦 Projet 06 — Séries temporelles : combien de glaces préparer demain ?

Ce projet consiste à construire des **modèles de séries temporelles** capables de prévoir le nombre de glaces vendues chaque jour à partir de l'historique des ventes de Bruno, un marchand de glaces.

L'objectif est de :

* 🍦 Analyser l'évolution des ventes de glaces au cours de plusieurs étés.

* 📊 Manipuler une **série temporelle** et respecter l'ordre chronologique des données.

* 🎯 Mettre en place des **baselines** simples pour servir de référence.

* 📈 Calculer l'**autocorrélation** d'une série temporelle.

* 🔍 Analyser les graphiques **ACF et PACF** pour identifier la mémoire de la série.

* 🧠 Comprendre et simuler un modèle **MA (Moving Average)**.

* 🔧 Entraîner un modèle **MA(3)** avec `statsmodels`.

* 🧠 Comprendre et entraîner un modèle **ARMA(1,1)**.

* 📉 Comparer les modèles avec la **MAE** et l'**AIC**.

* 🔬 Analyser les résidus avec le **test de Ljung-Box**.

* 🔮 Effectuer des prévisions à court terme et prévoir les **7 prochains jours**.

## 🛠️ Technologies

* Python

* NumPy

* Pandas

* Matplotlib

* Statsmodels

* ARIMA

* MA (Moving Average)

* ARMA (AutoRegressive Moving Average)

* Autocorrélation

* ACF / PACF

* Test de Ljung-Box

* MAE

* AIC

## 📂 Fichiers

```text
Projet_06/

├── data/
│   └── ventes_glaces.csv
│
├── projet_06.ipynb
├── utils.py
└── README.md
```

## ☁️ Environnement

Le projet a été réalisé en **Python** dans un environnement virtuel local.

La librairie principale utilisée pour les modèles de séries temporelles est **Statsmodels**.

Installation avec `uv` :

```bash
uv add statsmodels
```

Le notebook contient l'ensemble des étapes permettant de charger les données, analyser la série temporelle, entraîner les modèles et réaliser les prévisions.

Les fonctions présentes dans `utils.py` permettent notamment de faciliter la visualisation des ventes, des corrélogrammes et des prévisions.

## 📊 Résultat

L'analyse des ventes montre une importante variabilité du nombre de glaces vendues d'un jour à l'autre, mais également une **dépendance entre les jours successifs**.

Deux stratégies simples sont d'abord utilisées comme références :

* **Toujours la moyenne** : prévoir chaque jour avec la moyenne des ventes du jeu d'entraînement.

* **Comme hier** : utiliser les ventes du jour précédent pour prévoir le jour suivant.

La stratégie **« comme hier »** obtient une meilleure MAE que la stratégie basée uniquement sur la moyenne, ce qui montre qu'il existe une certaine mémoire dans la série temporelle.

L'étude de l'**autocorrélation (ACF)** permet ensuite d'identifier cette mémoire.

Sur la saison 2025 seule, l'ACF semble principalement significative jusqu'au retard 3, ce qui conduit à tester un modèle **MA(3)**.

En utilisant les données des quatre étés, la série dispose cependant d'une mémoire plus longue. L'ACF décroît progressivement et reste significative sur plusieurs retards.

Un modèle **ARMA(1,1)** est alors testé afin de représenter cette mémoire avec moins de coefficients.

Les modèles sont comparés à l'aide de :

* la **MAE** pour mesurer l'erreur de prévision ;

* l'**AIC** pour comparer la qualité des modèles en tenant compte de leur complexité ;

* le **test de Ljung-Box** pour vérifier si les résidus contiennent encore de la structure.

L'ARMA(1,1) obtient un **AIC plus faible** que le MA(3) et les résidus sont plus proches d'un bruit blanc.

Enfin, les modèles sont utilisés pour prévoir les **7 prochains jours**.

Le modèle MA(3) revient rapidement vers sa moyenne après quelques jours, tandis que l'ARMA(1,1) conserve progressivement l'effet des observations précédentes.

## 🎯 Ce que j'ai appris

* Comprendre ce qu'est une **série temporelle**.

* Comprendre pourquoi il ne faut **jamais mélanger aléatoirement** les données temporelles avant de séparer le train et le test.

* Mettre en place une **baseline** pour évaluer un modèle.

* Utiliser la **MAE (Mean Absolute Error)** pour mesurer une erreur de prévision.

* Comprendre et calculer l'**autocorrélation** manuellement.

* Comprendre la différence entre **ACF et PACF**.

* Lire et interpréter un **corrélogramme**.

* Comprendre le principe d'un modèle **MA(q)**.

* Simuler une série temporelle à partir de chocs aléatoires.

* Utiliser `enumerate()` pour parcourir une liste de coefficients avec leur indice.

* Utiliser **Statsmodels** pour entraîner des modèles de séries temporelles.

* Comprendre la notation `ARIMA(p, d, q)`.

* Entraîner un modèle **MA(3)** avec `ARIMA(0, 0, 3)`.

* Comprendre le rôle de la composante **AR (AutoRegressive)**.

* Entraîner un modèle **ARMA(1,1)** avec `ARIMA(1, 0, 1)`.

* Comprendre la différence entre **MA** et **moyenne mobile**.

* Comparer plusieurs modèles avec l'**AIC**.

* Analyser les résidus avec le **test de Ljung-Box**.

* Effectuer des prévisions avec `get_forecast()`.

* Réaliser des prévisions à plusieurs jours.

* Comprendre les limites des prévisions lorsque **l'horizon temporel augmente**.

* Comprendre pourquoi un modèle peut être efficace pour prévoir le lendemain mais devenir beaucoup moins précis pour prévoir une semaine entière.
