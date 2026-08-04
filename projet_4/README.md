# 🤖 Projet 04 — RAG & LLM : Assistant virtuel de l'Hôtel Le Belvédère

Ce projet consiste à construire un **assistant virtuel pour l'Hôtel Le Belvédère** capable de répondre aux questions des clients à partir de sa documentation officielle.

L'objectif est de :

* 🧠 Utiliser un **LLM** pour générer des réponses.
* 📄 Extraire et préparer les informations depuis des **fichiers PDF**.
* 🔢 Transformer les textes en **embeddings**.
* 🔎 Rechercher les rubriques les plus pertinentes avec la **similarité sémantique**.
* 🤖 Construire un pipeline **RAG (Retrieval-Augmented Generation)**.
* 📚 Retourner les **sources utilisées** pour chaque réponse.
* 🛡️ Éviter les hallucinations lorsque l'information n'est pas présente dans la documentation.

## 🛠️ Technologies

* Python
* Pandas
* NumPy
* PyPDF
* Hugging Face Transformers
* Sentence Transformers
* Scikit-learn
* Matplotlib
* Qwen 2.5 0.5B Instruct
* Embeddings
* t-SNE
* RAG

## 📂 Fichiers

```text
Projet_04/
├── projet_04.ipynb
├── data/
│   ├── informations_pratiques.pdf
│   └── ...
├── utils.py
└── README.md
```

## ☁️ Environnement

Le projet a été réalisé avec Google Colab en raison de problèmes rencontrés lors du téléchargement des modèles Hugging Face dans mon environnement local.

Après avoir terminé le projet, j'ai téléchargé le notebook depuis Google Colab et l'ai placé dans le dossier local du projet, comme pour les trois projets précédents, afin de conserver la même structure et de pouvoir le versionner sur GitHub.

C'est pourquoi le notebook contient au début de certaines cellules le code permettant de reconnecter Google Drive et de se positionner dans le dossier du projet :

``
import sys
import os
from google.colab import drive

drive.mount('/content/drive')

dossier_projet = '/content/drive/MyDrive/Colab Notebooks/projet_4'

os.chdir(dossier_projet)

sys.path.append(dossier_projet)

print("Dossier actuel :", os.getcwd())
print("Contenu du dossier :", os.listdir())
``

Ce code est nécessaire uniquement pour l'exécution sur Google Colab. Il permet au notebook d'accéder aux fichiers data/, à utils.py et aux autres ressources du projet stockées dans Google Drive.

## 📊 Résultat

Le projet compare trois approches :

1. **LLM seul** → risque d'hallucinations.
2. **Documentation complète dans le prompt** → réponses plus précises mais contexte important.
3. **RAG** → recherche des rubriques pertinentes avec les embeddings avant de générer la réponse.

Le système final permet de répondre aux questions à partir des informations pertinentes de l'hôtel tout en indiquant les **sources utilisées**.

## 🎯 Ce que j'ai appris

* Utiliser un **LLM pré-entraîné**.
* Extraire du texte depuis des **PDF**.
* Comprendre et générer des **embeddings**.
* Calculer une **similarité sémantique**.
* Utiliser **t-SNE** pour visualiser des embeddings.
* Mettre en place une recherche **Top-K**.
* Construire un pipeline **RAG complet**.
* Réduire le contexte envoyé au LLM pour obtenir des réponses plus ciblées.
* Limiter les **hallucinations** grâce à une documentation contrôlée.