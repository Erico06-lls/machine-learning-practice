# ✈️ Projet 07 — IA agentique : créer un agent IA qui planifie des vacances

Ce projet consiste à construire un **agent intelligent de planification de voyages** capable de composer un séjour personnalisé en fonction des préférences d'un voyageur, de sa destination, de ses dates et de son budget.

L'objectif est de développer un agent capable de rechercher des vols, sélectionner des hôtels selon les envies du voyageur, proposer des activités, ajuster automatiquement le programme lorsque le budget est dépassé et suggérer des dates alternatives.

Le projet permet également de découvrir comment donner à un agent la capacité d'effectuer une réservation après confirmation de l'utilisateur.

## 🎯 Objectifs du projet

- 🔍 Rechercher des vols disponibles à partir d'une base de données SQL.
- 🏨 Effectuer une recherche sémantique d'hôtels à partir de brochures PDF.
- 🧠 Utiliser des embeddings et la similarité cosinus pour identifier les hôtels correspondant aux préférences du voyageur.
- 💰 Construire un agent capable de respecter un budget en ajustant ses choix.
- ⚖️ Définir des règles de décision pour arbitrer entre les activités et les hôtels.
- 📅 Explorer les dates voisines afin de proposer des alternatives plus intéressantes.
- 📝 Conserver un journal des décisions et des ajustements effectués par l'agent.
- 📌 Enregistrer une réservation dans une base SQLite uniquement après confirmation.
- 🌐 Développer une interface web avec Streamlit pour interagir avec l'agent.

## 🧠 Fonctionnement de l'agent

L'agent reçoit une demande contenant six informations :

- Destination
- Date de départ
- Nombre de nuits
- Nombre de voyageurs
- Budget maximum par personne
- Envie ou préférences du voyageur

À partir de ces informations, il utilise différents outils pour construire un voyage.

**1. Recherche des vols**

Utilisation de requêtes SQL pour récupérer les vols disponibles selon la destination, la date, le nombre de voyageurs et les places restantes. Les résultats sont triés du moins cher au plus cher.

**2. Recherche des hôtels**

Utilisation des embeddings pour transformer les résumés des brochures en vecteurs numériques, puis calcul de la similarité cosinus entre les préférences du voyageur et les descriptions des hôtels.

**3. Recherche des activités**

Interrogation de la base de données pour récupérer les activités disponibles dans la destination choisie, avec leurs catégories, durées et prix.

## 💰 Gestion du budget et prise de décision

Lorsque le coût du voyage dépasse le budget maximum, l'agent entre dans une boucle de décision :

- Il commence par retirer les activités payantes les plus chères.
- Si nécessaire, il essaie des hôtels moins chers.
- Il conserve les activités gratuites, puisqu'elles ne font pas augmenter le coût du séjour.
- Il s'arrête lorsqu'il trouve une combinaison respectant le budget ou lorsqu'aucune solution n'est possible.

L'agent explore également les dates voisines afin de détecter des possibilités plus intéressantes, notamment lorsqu'un vol est moins cher un autre jour.

Il compare les alternatives en privilégiant le nombre d'activités conservées, puis le prix total.

## 📌 Réservation

Une fonctionnalité permet d'enregistrer le voyage dans la table `reservations` de la base de données SQLite.

Un mécanisme de confirmation protège l'utilisateur : aucune réservation n'est enregistrée tant que celui-ci n'a pas donné son accord.

## 🛠️ Technologies et notions utilisées

- Python
- Pandas
- NumPy
- SQLite / SQL
- Embeddings
- Similarité cosinus
- Recherche sémantique
- PDF et extraction de texte
- IA agentique et logique de décision
- Streamlit
- Jupyter Notebook
- Google Colab
- uv (gestion de l'environnement Python)

## 📂 Structure du projet

```text
Projet_07/
│
├── data/
│   └── ... (données et ressources du projet)
│
├── agent.py
├── app.py
├── utils.py
├── projet_07.ipynb
└── README.md
```

**Description des fichiers :**

- `agent.py` : contient la logique de l'agent et les fonctions permettant de planifier les voyages.
- `app.py` : contient l'interface utilisateur développée avec Streamlit.
- `utils.py` : regroupe les fonctions utilitaires utilisées dans le projet.
- `data/` : contient les données et ressources nécessaires au fonctionnement de l'application.
- `projet_07.ipynb` : notebook contenant les différentes étapes de développement et d'expérimentation.

## ☁️ Environnement de travail et exécution

Le développement et l'exécution du notebook `projet_07.ipynb` ont été réalisés sur **Google Colab**, à la suite d'un petit problème rencontré avec l'environnement initial.

Une fois le notebook terminé, je l'ai téléchargé et ajouté à mon repository GitHub afin de conserver le code source et de permettre sa consultation.

Par la suite, j'ai également développé et exécuté l'application Streamlit localement sur mon environnement Debian.

Pour lancer l'application, j'ai utilisé `uv` comme gestionnaire d'environnement Python.

Commande d'exécution :

```bash
uv run streamlit run app.py
```

Cette commande permet de démarrer l'application web Streamlit localement.

## 🎓 Ce que j'ai appris

- Comprendre le fonctionnement et l'architecture d'un agent IA.
- Construire des outils Python capables d'interroger une base de données.
- Écrire des requêtes SQL paramétrées pour éviter les injections SQL.
- Manipuler une base de données SQLite avec Python.
- Exploiter des documents PDF pour extraire des informations utiles.
- Utiliser des embeddings pour représenter des textes sous forme de vecteurs.
- Calculer une similarité cosinus pour effectuer une recherche sémantique.
- Construire une fonction de sélection d'hôtels basée sur les préférences utilisateur.
- Implémenter une boucle de décision avec des conditions `if`, `elif` et `else`.
- Utiliser `max()` avec `lambda` pour sélectionner les activités les plus coûteuses.
- Définir des règles d'arbitrage entre le choix des hôtels et les activités.
- Explorer des dates alternatives pour améliorer les propositions de voyage.
- Utiliser des tuples pour effectuer des comparaisons multicritères.
- Conserver un journal des décisions prises par un agent.
- Effectuer des insertions SQL avec `INSERT INTO` et `commit()`.
- Mettre en place un mécanisme de confirmation avant une action importante.
- Développer une interface web interactive avec Streamlit.
- Utiliser `uv` pour gérer l'environnement Python et exécuter une application.

## 🚀 Bilan

Ce projet m'a permis de découvrir concrètement l'**IA agentique** et de comprendre qu'un agent intelligent ne se limite pas à produire une réponse : il peut rechercher des informations, utiliser des outils, prendre des décisions, réévaluer ses choix et effectuer des actions selon des règles définies.

Il m'a également permis de réutiliser plusieurs notions abordées dans les projets précédents, notamment SQL, les embeddings et la recherche sémantique, pour construire un système plus complet.

Enfin, le passage du notebook à une application Streamlit m'a permis de mettre en pratique le développement d'une interface utilisateur autour d'un système intelligent.

**Projet réalisé dans le cadre du Cahier de Vacances Data & IA 2026 de Machine Learnia.**