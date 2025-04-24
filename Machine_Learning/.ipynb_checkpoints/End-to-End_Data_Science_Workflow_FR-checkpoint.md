# 📊 End-to-End Data Science Workflow  
**Auteur :** Gaspard-Fauvelle Angel
**Licence :** [CC BY-NC-SA 2.0](https://creativecommons.org/licenses/by-nc-sa/2.0/)

Here is the english version of the document [End-to-End Data Science Workflow](/.End-to-End_Data_Science_Workflow_Eng.md)

Ce document est le dernier d'une série :
- [SQL_CheatSheet_FR.ipynb](SQL_CheatSheet_FR.md)
- [Python_Pandas_FR.ipynb](Python_Pandas_CheatSheet_FR.md)
- [Numpy_Pandas_FR](NumPy_Pandas_CheatSheet_FR.md)
- [Data_Preprocessing_Methods_FR.ipynb](Data_Preprocessing_Methods_FR.md)

# 🧠 Table des Matières Dynamique
1. [🧭 I. Introduction au Sujet](#🧭-I.-Introduction-au-Sujet)
   - [1.1. Contexte de l'Étude / Objectifs / Questions de Recherche](#1.1.-Contexte-de-lÉtude-/-Objectifs-/-Questions-de-Recherche)
   - [1.2. Contraintes et Limitations](#1.2.-Contraintes-et-Limitations)
2. [🗂️ II. Configuration de l'Environnement](#🗂️-II.-Configuration-de-lEnvironnement)
   - [2.1. Imports](#2.1.-Imports)
   - [2.1.1. Bibliothèques](#2.1.1.-Bibliothèques)
   - [2.1.2. Chargement du Dataset](#2.1.2.-Chargement-du-Dataset)
   - [👁️ 2.2. Exploration Initiale - Aperçu de la Structure de Base du Dataset](#👁️-2.2.-Exploration-Initiale---Aperçu-de-la-Structure-de-Base-du-Dataset)
3. [🧹 III. Nettoyage et Transformation des Données - Gestion des Données Polluées](#🧹-III.-Nettoyage-et-Transformation-des-Données---Gestion-des-Données-Polluées)
4. [🧠 IV. Ingénierie des Caractéristiques](#🧠-IV.-Ingénierie-des-Caractéristiques)
5. [📈 V. Analyse Exploratoire des Données - EDA](#📈-V.-Analyse-Exploratoire-des-Données---EDA)
6. [🧪 VI. Analyse Inférentielle](#🧪-VI.-Analyse-Inférentielle)
7. [🤖 VII. Modélisation Prédictive](#🤖-VII.-Modélisation-Prédictive)
8. [📌 VIII. Analyse Prescriptive](#📌-VIII.-Analyse-Prescriptive)

---

## 🧭 I. Introduction au Sujet
### 1.1. Contexte de l'Étude / Objectifs / Questions de Recherche
Pourquoi avez-vous choisi ce dataset ? Quels sont les parties prenantes ? Quels sont les livrables à la fin ?
### 1.2. Contraintes et Limitations
- Planification de votre échéance / Combien de temps pour travailler dessus.
- Ressources de calcul, qualité des données et granularité

---

## 🗂️ II. Configuration de l'Environnement
### 2.1. Imports
#### 2.1.1. Bibliothèques
```python
# Importer les bibliothèques nécessaires
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px

# Importer les bibliothèques secondaires
from sklearn.sublibraries import MachineLearningsTools as mltools...
from scipy.sublibrairies import MathsTools as mathtools...
from datetime import date, datetime...

# Importer les bibliothèques de support
```

2.1.2. Chargement du Dataset
# Charger le dataset dans un DataFrame Pandas
df = pd.read_csv('votre_dataset.csv') # Pour lire un fichier CSV

# Lire les données depuis une URL
df_url = pd.read_csv('https://example.com/vos_donnees.csv') # Pour lire les données depuis une URL

# Lire un fichier Excel
df_excel = pd.read_excel('votre_fichier.xlsx', sheet_name='Feuille1') # Pour lire un fichier Excel

# Lire un fichier JSON
df_json = pd.read_json('votre_fichier.json') # Pour lire un fichier JSON

# Lire un fichier SQLite
import sqlite3
con = sqlite3.connect("database.sqlite") # Connecter Jupyter à database.sqlite
df = pd.read_sql_query("SELECT * from table", con) # Créer un DataFrame à partir d'une requête SQL dans la dernière variable

# Lire un fichier SQL (Même exemple que ci-dessus, avec une autre API)
from sqlalchemy import create_engine # À insérer dans les bibliothèques secondaires
engine = create_engine('sqlite:///votre_database.db')      # Créer un moteur de base de données SQLite
df_sql = pd.read_sql('SELECT * FROM votre_table', engine)  # Lire les données d'une table SQL

# Vérifier que le résultat de la requête SQL est stocké dans le dataframe
print(df.head())

# Lire un fichier Parquet
df_parquet = pd.read_parquet('votre_fichier.parquet') # Pour lire un fichier Parquet

# Les types de fichiers ci-dessus sont les principaux types de fichiers que vous rencontrerez en Data Science. Mais voici quelques autres types de fichiers ci-dessous comme :

# Lire un fichier HDF5
df_hdf5 = pd.read_hdf('votre_fichier.h5', key='votre_clé') # Pour lire un fichier HDF5

# Lire un fichier CERN ROOT
#from rootpy.io import ROOTFile # À insérer dans les bibliothèques secondaires
df_root = ROOT.TFile.Open('votre_fichier.root') # Pour lire un fichier ROOT

# Lire un fichier Feather
df_feather = pd.read_feather('votre_fichier.feather') # Pour lire un fichier Feather

# Lire un fichier à largeur fixe
#column_widths = [10, 15, 20]    ## Pour définir les largeurs des colonnes
df_fixed_width = pd.read_fwf('votre_fichier.txt', widths=column_widths) # Pour lire un fichier à largeur fixe

# Lire des données depuis le presse-papiers
df_clipboard = pd.read_clipboard() # Pour lire des données depuis le presse-papiers

### 👁️ 2.2. Exploration Initiale - Aperçu de la Structure de Base du Dataset
#### 2.2.1. Inspecter les dimensions et les types de données (Dictionnaire des variables avec .info(), et diagnostic approfondi de memory_usage)
```python
df.info(memory_usage='deep', show_counts='True')
```
#### 2.2.2. Inspecter un nombre fixe de lignes aléatoires avec .sample()
```python
df.sample(5)
```

---

## 🧹 III. Nettoyage et Transformation des Données - Gestion des Données Polluées
### 3.1. Gestion des Valeurs Manquantes (.isna(), si les données manquantes sont >x% ou <y%)
La meilleure méthode est d'ajouter une dimension aux colonnes avec des valeurs manquantes en créant une colonne booléenne (1 pour les valeurs manquantes et 0 pour les valeurs remplies)  
La deuxième méthode est, si les données manquantes sont <30%, d'utiliser la médiane ou le mode (préférable) pour remplir les valeurs manquantes  
En dernier recours, si les données manquantes sont >30%, supprimer ces lignes avec .dropna(), pour les colonnes, si les données manquantes sont >40%, .dropna('ColonnesASupprimer', axis=1)  
"Ces seuils (par exemple 30% pour les lignes, 40% pour les colonnes) sont empiriques et doivent être adaptés en fonction des connaissances du domaine, de la taille de l'échantillon et de la sensibilité du modèle."  
### 3.2. Gestion des Lignes en Double (.duplicated() et .drop_duplicates())
### 3.3. Gestion des Valeurs Aberrantes (Méthode IQR & Z_scores)
```python
# Détection pour la loi de distribution
z_scores = ((data['colonne1'] - moyennes) / écarts_types)
z_outliers = (np.abs(z_scores) > seuil_zscore).any(axis=1)

# Détection pour presque tout
q1, q3 = np.percentile(df['colonne1'], [25, 75])
iqr = q3 - q1
limite_inférieure = q1 - 1.5 * iqr
limite_supérieure = q3 + 1.5 * iqr
iqr_outliers = df[(df['colonne1'] >= limite_inférieure) & (df['colonne1'] <= limite_supérieure)]

# Avant de penser à supprimer les valeurs aberrantes, vérifiez si ces valeurs aberrantes sont des erreurs ou un signal valide (événements rares)
df_sans_z_outliers = data[~z_outliers].copy()
df_sans_iqr_outliers = df[(df['colonne1'] >= limite_inférieure) & (df['colonne1'] <= limite_supérieure)].copy()
```
### 3.4. Conversion de Type de Données - .astype(), pour réduire l'utilisation de la mémoire et optimiser les distinctions de colonnes
```python
# Utiliser un dictionnaire pour stocker les colonnes comme clés et les types que vous souhaitez définir comme valeurs
dict_convert = {
    'colonne1': 'dtypes'
}
# Créer une boucle pour appliquer la méthode .astype(valeurs_du_dict)
common_cols = set(df.columns) & set(dict_convert.keys())
# Vérifier que les colonnes spécifiées dans le dictionnaire 'conversions' existent bien dans le DataFrame avant de les convertir
for col in common_cols:
    df[col] = df[col].astype(dict_convert[col])
```
### 3.5. Gestion des Séries Temporelles (dates avec DateTimeIndex())
```python
df.set_index(df['colonneDate'], inplace=True)
```

---

##  🧠 IV. Ingénierie des Caractéristiques
### 4.1. Création de Nouvelles Caractéristiques - Numériques, Catégorielles et/ou Séries Temporelles
```python
# Compréhension de liste pour trier les types de données / Les séries temporelles (dates) peuvent être utilisées comme index, converties en ordinal/catégorie
types_séries_temporelles = ['datetime64']
caractéristiques_numériques = df.select_dtypes(include=[np.number]).columns.tolist()
caractéristiques_catégorielles = df.select_dtypes(exclude=np.number).columns.tolist()
caractéristiques_séries_temporelles = df.select_dtypes(include=types_séries_temporelles).columns.tolist()
```
### 4.2. Transformation des Caractéristiques
#### 4.2.1. Encodage des Variables Catégorielles
Méthodes de Prétraitement des Données

#### 4.2.2. Mise à l'Échelle et Normalisation / Standardisation des Variables Numériques
Méthodes de Prétraitement des Données

#### 4.2.3. Différenciation / Extraction de Caractéristiques des Variables de Séries Temporelles
Méthodes de Prétraitement des Données

---

## 📈 V. Analyse Exploratoire des Données - EDA
### 5.1. Analyse Univariée (Statistiques Descriptives)
#### 5.1.1. Caractéristiques Numériques (Quantitatives)
```python
# Imprimer les descriptions statistiques
```
#### 5.1.2. Caractéristiques Catégorielles (Qualitatives)
#### 5.1.3. Caractéristiques de Séries Temporelles (Date)
```python
# Fréquences, pourcentages, fractions et/ou fréquences relatives
```
### 5.2. Analyse Bivariée / Multivariée
```python
# Rééchantillonnage (.resample()), Moyenne Mobile (.rolling()), Fonction Pondérée Exponentielle (.ewm())
```
#### 5.2.1. Numérique vs Numérique
```python
# Graphiques comparatifs entre 2 variables ou plus (Nuage de Points, Courbes de Régression/Tendances, Graphique à Bulles, LmPlot, PairPlot, histogramme, etc...)
```
#### 5.2.2. Catégorielle vs Catégorielle
```python
# Graphiques comparatifs entre 2 variables ou plus (Histogramme Groupé/Empilé, MosaicPlot, Heatmap, PairPlot, etc...)
```
#### 5.2.3. Catégorielle vs Numérique
```python
# Graphiques comparatifs entre 2 variables ou plus (BoxPlot, ViolinPlot, Barres de Moyenne/Erreur, Dot/Strip Plot, CatPlot, PairPlot, histogramme, etc...)
```
#### 5.2.4. Séries Temporelles vs Numérique/Catégorielle
```python
# Graphiques comparatifs entre 2 variables ou plus (statsmodels.tsa.seasonal_decompose, Histogramme, PairPlot, etc...)
```

---

## 🧪 VI. Analyse Inférentielle
### 6.1. Définition des Hypothèses
Définissez votre Hypothèse Nulle (H0)  
### 6.2. Tests d'Hypothèses
#### 6.2.1. Tests d'Hypothèse de Normalité et d'Homoscédasticité (homogénéité de la variance) (Tests préliminaires avant de choisir des Tests Paramétriques ou Non Paramétriques)
```python
# Tests de Normalité : Test de Shapiro-Wilk, Test de Kolmogorov-Smirnov, Test d'Anderson-Darling

# Tests d'Homoscédasticité : Test de Levene, Test de Bartlett

# Test d'Autocorrélation : Test de Durbin-Watson, Test de White

# Test de Multicolinéarité : VIF (Facteur d'Inflation de la Variance)
```
#### 6.2.2. Tests Paramétriques (Données sans valeurs aberrantes, suivant une loi de distribution)
```python
# Pour les données uniquement numériques (Analyse de Corrélation : Corrélation de Pearson, Test T de Régression Linéaire)

# Pour les données uniquement catégorielles (Intervalles de Confiance) : Régression Logistique, Modèles Log-Linéaires

# Pour les données numériques et catégorielles (Analyse de la Variance) : Test T de Student, MANOVA/ANOVA (Analyse de la Variance)
```
#### 6.2.3. Tests Non Paramétriques (Robustes face aux données avec valeurs aberrantes et indifférents à la loi de distribution)
```python
# Pour les données uniquement numériques (Analyse de Corrélation) : Corrélation de Spearman, Corrélation de Kendall (Tau)

# Pour les données uniquement catégorielles (Analyse de la Variance) : Chi², Test Exact de Fisher, Test de McNemar, Test de Cochran-Armitage pour les Tendances (Analyse de Corrélation)

# Pour les données numériques et catégorielles (Analyse de la Variance) : Test de Mann-Whitney, Test des Rangs Signés de Wilcoxon, ANOVA de Kruskal-Wallis
```
#### 6.3. Conclusion des Hypothèses
#### 6.3.1. H0 ou H1 est valide
#### 6.3.2. Sélection des Caractéristiques
```python
# À partir des différents tests, quelles colonnes allez-vous conserver ?
df = df[['colonne1', 'colonne2', '...', 'colonneN']]
# Si vous avez plus de colonnes à conserver qu'à supprimer, quelles colonnes allez-vous supprimer ?
df = df.drop(['colonne1', 'colonne2', '...', 'colonneN'], axis=1])
```

---

## 🤖 VII. Modélisation Prédictive
### 7.1. Prétraitement des Données pour la Modélisation
#### 7.1.1. Séparation des Caractéristiques / Cible
```python
# Caractéristiques & Cible
X = df.drop(['ColonneCible'], axis=1)
y = df[['ColonneCible']]
```
#### 7.1.2. Séparation Entraînement-Test (train_test_split comme tts) et Séparation des Séries Temporelles (TimeSeriesSplit comme tss)
```python
# La partition commune est 80/20 (80% pour l'Entraînement et 20% pour le Test), le mélange doit être défini comme True
X_train, X_test, y_train, y_test = tts(X, y, train_size=0.8, random_state=1, shuffle=True, stratify=None)
```
#### 7.1.3. Stratégie de Validation Croisée (Réglage des Hyperparamètres)
```python
# Hyperparamètres globaux : Recherche en Grille (GridSearchCV), Recherche Aléatoire (RandomizedSearchCV), Optimisation Bayésienne (BayesianSearchCV Optuna, Hyperopt)

# Hyperparamètre de régression uniquement : Réglage intégré de la validation croisée

# Hyperparamètre de classificateur uniquement : Validation croisée avec échantillonnage stratifié (StratifiedKFold)
```
### 7.2. Entraînement et Évaluation du Modèle
```python
# Régresseurs (par exemple, Régression Linéaire, Régression des Forêts Aléatoires, Régression par Gradient Boosting...)

# Classificateurs (par exemple, Régression Logistique, Arbres de Décision, Classificateur de Forêts Aléatoires, Machines à Vecteurs de Support)

# Pipelines pour le prétraitement et l'entraînement

# Techniques de validation croisée (par exemple, Group/K Fold, StratifiedKFold, TimeSeriesSplit pour les données séquentielles)
```
#### 7.2.1. Entraînement du Modèle sur l'Ensemble d'Entraînement
```python
# Régresseurs (par exemple, Régression Linéaire, Régression des Forêts Aléatoires, Régression par Gradient Boosting...)

# Classificateurs (par exemple, Régression Logistique, Arbres de Décision, Classificateur de Forêts Aléatoires, Machines à Vecteurs de Support)

# Pipelines pour le prétraitement et l'entraînement

# Techniques de validation croisée (par exemple, Group/K Fold, StratifiedKFold, TimeSeriesSplit pour les données séquentielles)
```
#### 7.2.2. Analyse des Erreurs et Métriques
```python
# Métriques de Régression : Erreur Absolue Moyenne (MAE), Erreur Quadratique Moyenne (MSE), Erreur Quadratique Moyenne Racine (RMSE), R-carré (R²)

# Analyse du Classificateur : Précision, Rappel, Score F1 et Analyse Visuelle des Erreurs comme la Matrice de Confusion, Courbe ROC / AUC, Courbes Précision-Rappel
```
#### 7.2.3. Évaluation Visuelle
```python
# Régression : Nuages de Points (réel vs prédit), Graphiques en Ligne, Graphiques des Résidus, Courbes d'Apprentissage, Box Plots

# Classificateur : Heatmaps (pour les Matrices de Confusion), Courbes ROC, Courbes Précision-Rappel
```
### 7.3. Généralisation et Cas d'Utilisation Réels
```python
# Régression : Nuages de Points (réel vs prédit), Graphiques en Ligne, Graphiques des Résidus, Courbes d'Apprentissage, Box Plots

# Classificateur : Heatmaps (pour les Matrices de Confusion), Courbes ROC, Courbes Précision-Rappel

```
#### 7.3.1. Prédiction sur les Ensembles de Test Réels
```python
# Inférence sur des données non vues/du monde réel en utilisant le modèle entraîné

# Utiliser les pipelines de prétraitement/ingénierie des caractéristiques sur les données de test réelles

# Générer des prédictions via model.predict (par lots ou en continu)

# Effectuer l'évaluation finale et l'analyse des erreurs sur les performances de l'ensemble de test réel
```
#### 7.3.2. Considérations de Déploiement (facultatif)
```python
# Sérialisation et exportation du modèle (par exemple, pickle, joblib, ONNX, SavedModel)

# Cadres de déploiement d'API (par exemple, Flask, FastAPI, TensorFlow Serving, TorchServe)

# Conteneurisation et orchestration (par exemple, Docker, Kubernetes)

# Surveillance, journalisation et optimisation des performances pour la production
```
## 📌 VIII. Analyse Prescriptive
### 8.1. Recommandations Commerciales
- Traduire les insights analytiques en stratégies exploitables.
- Utiliser le storytelling de données pour informer la prise de décision stratégique.
- Utiliser des cadres tels que l'analyse SWOT, la définition des KPI et la surveillance des performances.
- Engager des experts du domaine pour valider les recommandations.
### 8.2. Scénarios Hypothétiques / Simulations
- Développer des modèles de simulation pour explorer des scénarios futurs alternatifs.
- Employer des méthodes comme les simulations de Monte Carlo et l'analyse de sensibilité.
- Utiliser la planification de scénarios pour évaluer l'impact de différentes hypothèses.
- Évaluer les risques et les incertitudes dans diverses situations opérationnelles ou de marché.
### 8.3. Conception de Tableaux de Bord (Facultatif pour les Parties Prenantes)
- Construire des tableaux de bord interactifs et informatifs pour la visualisation des données en temps réel.
- Utiliser des outils tels que Tableau, PowerBI ou Plotly Dash pour la facilité d'utilisation et l'accessibilité.
- Se concentrer sur les principes de conception centrée sur l'utilisateur : clarté, simplicité et insights exploitables.
- Assurer l'évolutivité, la maintenabilité et la sécurité des données dans le déploiement des tableaux de bord.

---

🎉 Félicitations pour avoir suivi ce guide de Data Science de bout en bout !  
Vous êtes maintenant prêt(e) à passer à l'étape suivante et publier votre projet.  
Rendez-vous sur [Git & GitHub Environment](01-Github_Git_Init.md) pour apprendre à importer votre travail sur GitHub et le rendre visible.  


_Edited: 2025-04-22_