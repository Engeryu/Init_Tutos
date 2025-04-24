# Méthodes de Prétraitement des Données
**Auteur:** Gaspard-Fauvelle Angel  
**License:** [CC BY-NC-SA 2.0](https://creativecommons.org/licenses/by-nc-sa/2.0/)  

## Table des matières
- [Ingénierie des Caractéristiques](#Ingénierie-des-Caractéristiques)
  - [Mise à l’échelle, Normalisation et Standardisation](#Mise-à-léchelle-Normalisation-et-Standardisation)
- [Encodage des Variables Catégorielles](#Encodage-des-Variables-Catégorielles)
- [Découpage des Données](#Découpage-des-Données)
- [Utilitaires de Prétraitement](#Utilitaires-de-Prétraitement)

---

## Ingénierie des Caractéristiques

### Mise à l’échelle, Normalisation et Standardisation

| Méthode / Outil (Sklearn uniquement) | Description                                           |
|--------------------------------------|-------------------------------------------------------|
| `MinMaxScaler` (sklearn)             | Met à l’échelle les caractéristiques entre 0 et 1     |
| `StandardScaler` (sklearn)           | Standardise les données (moyenne = 0, écart-type = 1) |
| `RobustScaler` (sklearn)             | Utilise la médiane et l’IQR (robuste aux valeurs extrêmes) |
| `Normalizer` (sklearn)               | Normalise chaque échantillon individuellement         |

---

## Encodage des Variables Catégorielles

| Méthode / Outil               | Description                                            |
|-------------------------------|--------------------------------------------------------|
| `OrdinalEncoder` (sklearn)    | Encode les variables ordinales en entiers ordonnés    |
| `LabelEncoder` (sklearn)      | Encode les catégories ordinales/rangées               |
| `pd.get_dummies()` \ `OneHotEncoder` (sklearn) | Encode les variables nominales         |

---

## Découpage des Données

| Méthode / Outil               | Description                                             |
|-------------------------------|---------------------------------------------------------|
| `train_test_split()`          | Sépare les données en ensembles d’entraînement/test (taille normale) |
| `StratifiedKFold`             | Maintient les proportions des classes entre les plis (classification, jeu plus grand) |
| `KFold` / `GroupKFold`        | Méthodes de validation croisée avec ou sans regroupement (régression, jeu plus grand) |
| `TimeSeriesSplit`             | Méthodes de validation croisée faite pour les jeux de données incluant une variable date/datetime que vous aurez mis en tant qu'index |

---

## Utilitaires de Prétraitement

| Outil / Concept               | Description                                                   |
|-------------------------------|----------------------------------------------------------------|
| `fit()` / `transform()` / `fit_transform()` | Méthodes d’application de transformations           |
| `Pipeline` (sklearn)          | Enchaîne les étapes de prétraitement et de modélisation       |
| `ColumnTransformer` (sklearn) | Applique des transformateurs à des colonnes spécifiques        |
| `FunctionTransformer`         | Intègre des fonctions personnalisées dans un pipeline         |

---

**Vous pouvez vous rediriger vers la feuille finale sur [End-To-End Data Science Workflow](End-to-End_Data_Science_Workflow_FR.ipynb)**

_Edité: 22/04/2025_
