# 🧠 Projet Vision DL (CIFAR-10) — Notebook Colab Complet

**Auteur** : Juvenal MALECOU  
**Date** : 2025-09-28

## 🚀 Objectif

Construire un pipeline complet de classification d'images de A à Z sur CIFAR-10 :

- Prétraitement & Augmentations
- CNN from scratch
- Fine-tuning ResNet50
- Explicabilité avec Grad-CAM
- Comparaison des performances
- (Bonus) Démo interactive avec Gradio

Chaque choix est commenté et justifié !

---

## ⚙️ 0) Préparation de l'environnement

- Import des librairies nécessaires (PyTorch, torchvision, sklearn…)
- Gestion des seeds pour reproductibilité

## 🧹 1) Données & Prétraitement

- Utilisation du dataset CIFAR-10 (10 classes, 32×32, 60k images)
- Normalisation avec moyenne/écart-type officiel
- Augmentations (flip, crop, jitter) pour robustesse
- DataLoader pour batching & shuffle
- Visualisation des batches et des augmentations

## 🏗️ 2) CNN from Scratch

- Architecture custom : Conv2d → BatchNorm → ReLU → MaxPool → Dropout → FC
- Entraînement sur 8 epochs, suivi des courbes loss/accuracy
- Sauvegarde du meilleur modèle
- Rapport de classification & matrice de confusion

## 🔥 3) Explicabilité : Grad-CAM

- Implémentation Grad-CAM (custom, hooks PyTorch)
- Visualisation des zones d’attention sur les images pour le CNN et ResNet50
- Permet d’interpréter les prédictions du modèle

## 🏎️ 4) Transfer Learning : ResNet50

- Fine-tuning du ResNet50 pré-entraîné sur ImageNet
- Adaptation de la tête de classification à 10 classes
- Bloc layer4 débloqué pour finetune léger
- Entraînement sur 6 epochs, suivi des courbes loss/accuracy

## ⚖️ 5) Comparaison des performances

- Comparaison des meilleures accuracies :
  - CNN from scratch : **~0.66**
  - ResNet50 finetuné : **~0.78**
  - Amélioration absolue : **+12 points**
- Rapport détaillé (précision, recall, f1-score par classe)

## 🎛️ 6) (Bonus) Démo interactive avec Gradio

- Mini-app Gradio pour tester le modèle sur vos images
- Affichage des prédictions Top-5 + Grad-CAM overlay
- Compatible Colab & Hugging Face Spaces

---

## 📊 Résultats principaux

| Modèle                | Accuracy (test) | Commentaire           |
|-----------------------|-----------------|-----------------------|
| CNN from scratch      | ~0.66           | Baseline, simple CNN  |
| ResNet50 finetuné     | ~0.78           | +12 points vs CNN     |

- **Explicabilité** : Grad-CAM intégré pour interpréter les prédictions.
- **Démo** : mini-app Gradio pour test manuel.




## 📎 Pour lancer le notebook

1. Ouvrez `Projet_Vision_CIFAR10.ipynb` dans Google Colab.
2. Exécutez toutes les cellules.
3. Pour tester la démo Gradio, lancez `demo.launch()` en fin de notebook.

---

## 📦 Fichiers

- `Projet_Vision_CIFAR10.ipynb` : Notebook complet
- `best_cnn.pth` : Poids du meilleur CNN
- `best_resnet50.pth` : Poids du meilleur ResNet50

---

## 🤝 Contact

Pour toute question, contactez [Juvenal MALECOU](https://github.com/MNJuvenal).
