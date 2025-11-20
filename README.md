# ANIP Computer Vision Challenge 2025

## 📋 Description du Projet

Ce dépôt contient les solutions développées pour le challenge de vision par ordinateur ANIP 2025 organisé sur Kaggle. Le challenge porte sur trois tâches principales de vision par ordinateur : la reconnaissance faciale, l'estimation d'âge et l'OCR (reconnaissance optique de caractères) avec détection de fraude.

**Lien du Challenge:** [ANIP - Reconnaissance Faciale, Estimation d'Âges & OCR](https://www.kaggle.com/competitions/anip-reconnaissance-faciale-estimation-ages-ocr/overview)

## 🎯 Objectifs du Challenge

Le challenge ANIP 2025 propose trois tâches distinctes mais complémentaires dans le domaine de la vision par ordinateur :

### Tâche 1 : Reconnaissance Faciale (Face Recognition)
Développer un système capable d'identifier si deux images représentent la même personne. Cette tâche est cruciale pour les systèmes de sécurité, l'authentification biométrique et la gestion d'identité.

**Objectif :** Classifier des paires d'images pour déterminer si elles montrent la même personne (1) ou des personnes différentes (0).

### Tâche 2 : Estimation d'Âge (Age Estimation)
Créer un modèle capable d'estimer l'âge d'une personne à partir de son image faciale. Cette application trouve son utilité dans le contrôle d'accès, le marketing ciblé et les services personnalisés.

**Objectif :** Prédire l'âge d'une personne avec une précision maximale à partir d'images faciales.

### Tâche 3 : OCR & Détection de Fraude (OCR & Fraud Detection)
Développer un système d'extraction de texte à partir de documents d'identité (permis de conduire, passeports, cartes d'identité) provenant de différents pays, tout en structurant les informations extraites selon un format JSON prédéfini.

**Objectif :** Extraire et structurer les informations des documents d'identité de manière précise et fiable.

## 📁 Structure du Projet

```
ANIP-Computer-Vision-Challenge-2025/
│
├── Task1_Stephane_Bah/
│   ├── Tache_1_Bah_Stephane_Notebook_1510.ipynb    # Notebook de reconnaissance faciale
│   └── stefbah_submission_task1.csv                # Fichier de soumission pour la tâche 1
│
├── Task2_Stephane_Bah/
│   ├── Tache_2_Bah_Stephane_Notebook_1510.ipynb    # Notebook d'estimation d'âge
│   └── stefbah_submission_task2.csv                # Fichier de soumission pour la tâche 2
│
├── Task3_Stephane_Bah/
│   ├── Tache_3_Bah_Stephane_Notebook_1510.ipynb    # Notebook OCR & détection de fraude
│   └── stefbah_submission_task3_part1.csv          # Fichier de soumission pour la tâche 3
│
└── Face & Skin Detection/
    ├── 268877114.pdf                               # Documentation de référence
    ├── Anggo_2018_J._Phys.__Conf._Ser._1028_012119.pdf
    └── FaceRecognitionusingEigenfaces.pdf
```

## 🛠️ Technologies Utilisées

- **Python 3.x** - Langage de programmation principal
- **PyTorch** - Framework de deep learning pour l'entraînement des modèles
- **torchvision** - Bibliothèque pour le traitement d'images et modèles pré-entraînés
- **NumPy** - Calculs numériques et manipulation de tableaux
- **Pandas** - Manipulation et analyse de données
- **Matplotlib** - Visualisation de données
- **PIL/Pillow** - Traitement d'images
- **dlib** - Détection de visages et landmarks faciaux
- **facenet-pytorch** - Implémentation de FaceNet pour la reconnaissance faciale
- **OpenCV** - Traitement d'images et vision par ordinateur

## 🚀 Installation et Utilisation

### Prérequis

```bash
# Installer Python 3.x (recommandé: Python 3.8+)
# Installer pip (gestionnaire de packages Python)
```

### Installation des dépendances

```bash
# Installation de PyTorch (ajuster selon votre configuration GPU/CPU)
pip install torch torchvision

# Installation des autres dépendances
pip install numpy pandas matplotlib pillow
pip install opencv-python
pip install facenet-pytorch
```

### Téléchargement des modèles pré-entraînés

Certains notebooks utilisent des modèles pré-entraînés comme le détecteur de landmarks de dlib :

```bash
# Le modèle de landmarks faciaux dlib (shape_predictor_68_face_landmarks.dat)
# sera téléchargé automatiquement lors de l'exécution des notebooks
```

### Exécution des Notebooks

1. **Pour la Tâche 1 (Reconnaissance Faciale) :**
   ```bash
   jupyter notebook Task1_Stephane_Bah/Tache_1_Bah_Stephane_Notebook_1510.ipynb
   ```

2. **Pour la Tâche 2 (Estimation d'Âge) :**
   ```bash
   jupyter notebook Task2_Stephane_Bah/Tache_2_Bah_Stephane_Notebook_1510.ipynb
   ```

3. **Pour la Tâche 3 (OCR & Détection de Fraude) :**
   ```bash
   jupyter notebook Task3_Stephane_Bah/Tache_3_Bah_Stephane_Notebook_1510.ipynb
   ```

## 📊 Approches Techniques

### Tâche 1 : Reconnaissance Faciale

L'approche utilisée pour la reconnaissance faciale combine plusieurs techniques :

- **Détection de visages** avec dlib
- **Extraction de caractéristiques** avec FaceNet (facenet-pytorch)
- **Alignement facial** basé sur les landmarks
- **Comparaison d'embeddings** pour déterminer la similarité entre deux visages

**Format de soumission :** CSV avec colonnes `Shot1,Shot2` contenant les identifiants des paires d'images

### Tâche 2 : Estimation d'Âge

L'approche pour l'estimation d'âge utilise :

- **Prétraitement d'images** incluant détection et alignement des visages
- **Modèles de deep learning** basés sur des architectures CNN pré-entraînées
- **Fine-tuning** sur le dataset spécifique de la compétition
- **Régression** pour prédire l'âge exact

**Format de soumission :** CSV avec colonnes `ID,Age` contenant l'identifiant et l'âge prédit

### Tâche 3 : OCR & Détection de Fraude

L'approche pour l'OCR et la détection de fraude comprend :

- **Prétraitement d'images** de documents d'identité
- **OCR (Reconnaissance Optique de Caractères)** pour extraire le texte
- **Parsing et structuration** des informations extraites
- **Validation** pour détecter les incohérences et fraudes potentielles

**Format de soumission :** CSV avec colonnes `Country/Card,FileName,Raw OCR,GT` où GT contient un JSON structuré avec les champs :
- `name` : Nom complet
- `address` : Adresse
- `birthday` : Date de naissance
- `gender` : Sexe
- `class` : Classe du permis
- `issue_date` : Date d'émission
- `expire_date` : Date d'expiration
- `license_number` : Numéro de licence
- `height` : Taille
- `weight` : Poids
- `eye_color` : Couleur des yeux
- `DD` : Numéro DD

## 📈 Résultats et Soumissions

Les fichiers de soumission sont disponibles dans chaque dossier de tâche :
- `stefbah_submission_task1.csv` - Résultats de reconnaissance faciale
- `stefbah_submission_task2.csv` - Résultats d'estimation d'âge
- `stefbah_submission_task3_part1.csv` - Résultats OCR et détection de fraude

## 📚 Références et Documentation

Le dossier `Face & Skin Detection` contient des articles de recherche et de la documentation de référence sur :
- Les techniques de reconnaissance faciale
- L'utilisation des Eigenfaces
- Les méthodes de détection de visages et de peau

## 👤 Auteur

**Stéphane Bah**

## 📝 Licence

Ce projet est développé dans le cadre du challenge ANIP Computer Vision Challenge 2025.

## 🤝 Contribution

Ce dépôt contient les solutions personnelles pour le challenge Kaggle ANIP 2025. Pour toute question ou suggestion, n'hésitez pas à ouvrir une issue.

## 🔗 Liens Utiles

- [Challenge Kaggle ANIP 2025](https://www.kaggle.com/competitions/anip-reconnaissance-faciale-estimation-ages-ocr/overview)
- [Documentation PyTorch](https://pytorch.org/docs/stable/index.html)
- [FaceNet Paper](https://arxiv.org/abs/1503.03832)
- [dlib Documentation](http://dlib.net/)

---

*Dernière mise à jour : Novembre 2025*
