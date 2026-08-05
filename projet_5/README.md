# 🐟 Projet 05 — Deep Learning & Vision : Encadrer et nommer les poissons

Ce projet consiste à construire un **détecteur de poissons** capable de localiser et d'identifier 13 espèces de poissons d'aquarium à partir d'une image.

L'objectif est de :

* 🐟 Détecter plusieurs poissons présents dans une même image.
* 📦 Localiser chaque poisson avec une **bounding box**.
* 🏷️ Identifier l'espèce de chaque poisson.
* 🧠 Utiliser un modèle **Faster R-CNN pré-entraîné**.
* 🔧 Effectuer un **fine-tuning** sur les 13 espèces du dataset.
* 📉 Suivre l'évolution des différentes **losses** pendant l'entraînement.
* 🔍 Réutiliser le modèle fine-tuné pour effectuer des prédictions sur de nouvelles images.

## 🛠️ Technologies

* Python
* PyTorch
* Torchvision
* Pandas
* PIL
* Matplotlib
* KaggleHub
* Faster R-CNN
* MobileNetV3
* Dataset / DataLoader
* Fine-tuning
* Object Detection

## 📂 Fichiers

```text
Projet_05/
├── projet_05.ipynb
├── utils.py
└── README.md
```

## ☁️ Environnement

L'entraînement a été réalisé avec **Google Colab**, car le fine-tuning d'un modèle Faster R-CNN demande davantage de ressources que les projets précédents.

Après avoir terminé le projet, j'ai **téléchargé le notebook depuis Google Colab et l'ai placé dans le dossier local du projet**, comme pour les projets précédents, afin de conserver la même organisation et de pouvoir le versionner sur GitHub.

Le notebook contient donc du code permettant de connecter Google Drive et d'accéder au dossier du projet lors de son exécution sur Colab.

## 📊 Résultat

Le modèle pré-entraîné sur COCO ne reconnaissait pas les espèces de poissons du dataset.

Après fine-tuning, le modèle est capable de :

* détecter les poissons ;
* encadrer chaque poisson ;
* identifier leur espèce parmi les **13 espèces apprises**.

Le modèle peut également être utilisé sur des images de résolution différente, notamment des photos prises avec un téléphone.

## 🎯 Ce que j'ai appris

* Comprendre la différence entre **classification et détection d'objets**.
* Utiliser **Faster R-CNN** avec PyTorch/Torchvision.
* Manipuler un **Dataset** et un **DataLoader** PyTorch.
* Comprendre les **bounding boxes** et les labels.
* Préparer des données au format YOLO pour PyTorch.
* Comprendre le fonctionnement du **fine-tuning**.
* Geler une partie d'un réseau avec `requires_grad`.
* Remplacer la tête de classification d'un modèle pré-entraîné.
* Écrire une **boucle d'entraînement PyTorch**.
* Suivre et interpréter les différentes **losses**.
* Réaliser des prédictions et afficher les bounding boxes.
* Comprendre les limites d'un modèle entraîné sur un nombre limité d'espèces.
