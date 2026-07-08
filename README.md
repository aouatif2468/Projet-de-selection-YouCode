# Projet de sélection — Exploration de données avec Python
### Parcours Développement en Intelligence Artificielle — YouCode

## 1. Présentation rapide du besoin

L'entreprise **Sell4All**, spécialisée dans la vente de vêtements d'occasion en ligne, souhaite intégrer une première fonctionnalité d'intelligence artificielle de recommandation de produits. Avant de développer cette fonctionnalité, il est nécessaire d'explorer et de nettoyer les données clients disponibles (`dataset-sell4all.csv`) afin de vérifier leur qualité et leur adéquation avec un futur projet d'IA.

Ce projet réalise cette première exploration : lecture des données, résumé technique, statistiques descriptives (moyenne/médiane), visualisation des dépenses par pays, puis nettoyage (suppression des dépenses < 10 €, suppression des doublons) et export d'un fichier CSV propre.

## 2. Étapes suivies pendant les 3 jours

- **Jour 1** : Installation de l'environnement (Miniconda, Jupyter Notebook, Pandas, Matplotlib) ; prise en main du dataset ; lecture du fichier CSV et affichage des 5 premières lignes.
- **Jour 2** : Réalisation du résumé technique (`.info()`), explication des notions (entrées, non-null, types de données) ; calcul des statistiques (moyenne, médiane) sur `Age` et `Customer spendings` ; question bonus sur la médiane d'âge par pays.
- **Jour 3** : Création de la visualisation (graphique à barres des dépenses par pays) ; nettoyage des données (dépenses < 10 €, doublons) ; export du fichier CSV nettoyé ; rédaction du README et mise en ligne sur GitHub.

## 3. Fonctionnalités développées

- Lecture du fichier `dataset-sell4all.csv` avec Pandas.
- Affichage des 5 premières lignes du dataset.
- Résumé technique complet (nombre de lignes, colonnes, types de données) avec explication dans une cellule Markdown.
- Calcul de la moyenne et de la médiane des colonnes `Age` et `Customer spendings`.
- Calcul bonus de la médiane d'âge par pays (`groupby`).
- Graphique à barres des dépenses totales des clients par pays (Matplotlib).
- Nettoyage des données :
  - suppression des lignes avec moins de 10 € de dépenses,
  - suppression des lignes en doublon.
- Export d'un nouveau fichier CSV nettoyé (`dataset-sell4all-clean.csv`) contenant uniquement les colonnes `Country`, `Âge`, `Gender`, `Customer spendings`.

## 4. Difficultés rencontrées et solutions

- **Valeurs manquantes dans la colonne Age** : identifiées grâce à `.info()` (colonne `Non-Null Count` inférieure au nombre total de lignes). Elles ont été conservées à ce stade (traitement en amont d'un futur pipeline IA) mais clairement signalées dans le résumé technique.
- **Distinction moyenne / médiane** : pour bien qualifier la donnée, il fallait comprendre que la moyenne peut être biaisée par des valeurs extrêmes de dépenses ; la médiane donne une vision plus fidèle de la tendance centrale.
- **Ordre des opérations de nettoyage** : il fallait filtrer les dépenses avant de dédupliquer pour éviter d'incohérences dans le comptage des lignes supprimées.

## 5. Mode d'exécution du projet

### Prérequis
- Miniconda installé (Python 3.x)
- Jupyter Notebook
- Bibliothèques Python : `pandas`, `matplotlib`

### Installation
```bash
conda create -n sell4all python=3.11
conda activate sell4all
pip install pandas matplotlib jupyter
```

### Lancer le projet
```bash
jupyter notebook exploration_donnees_sell4all.ipynb
```
Puis exécuter les cellules dans l'ordre (`Kernel > Restart & Run All`).

### Fichiers du dépôt
- `exploration_donnees_sell4all.ipynb` : notebook contenant tout le code, les résultats et les explications.
- `dataset-sell4all.csv` : jeu de données brut (à remplacer par le fichier fourni si différent).
- `dataset-sell4all-clean.csv` : jeu de données nettoyé, résultat final.
- `README.md` : ce fichier.
