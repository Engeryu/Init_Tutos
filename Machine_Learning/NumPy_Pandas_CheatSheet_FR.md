# Numpy & Pandas Methods
**Auteur:** Gaspard-Fauvelle Angel  
**License:** [CC BY-NC-SA 2.0](https://creativecommons.org/licenses/by-nc-sa/2.0/)  

## Table des matières
- [Méthodes Pandas](#Méthodes-Pandas)
  - [Inspection des données](#Inspection-des-données)
  - [Nettoyage des données](#Nettoyage-des-données)
  - [Manipulation des données](#Manipulation-des-données)
  - [Agrégation et Groupement](#Agrégation-et-Groupement)
  - [Fusion et Jointure](#Fusion-et-Jointure)
  - [Restructuration](#Restructuration)
  - [Méthodes Statistiques](#Méthodes-Statistiques)
- [Méthodes NumPy](#Méthodes-NumPy)
  - [Création de tableaux](#Création-de-tableaux)
  - [Manipulation de tableaux](#Manipulation-de-tableaux)
  - [Fonctions Mathématiques](#Fonctions-Mathématiques)
  - [Fonctions Statistiques](#Fonctions-Statistiques)
  - [Algèbre Linéaire](#Algèbre-Linéaire)

---

## Méthodes Pandas

### Inspection des données

| Méthode            | Description                                      |
|--------------------|--------------------------------------------------|
| `.head()`          | Retourne les premières lignes                    |
| `.tail()`          | Retourne les dernières lignes                    |
| `.info()`          | Fournit un résumé du DataFrame                   |
| `.describe()`      | Génère des statistiques descriptives             |
| `.shape`           | Retourne un tuple des dimensions                 |
| `.dtypes`          | Retourne les types de données de chaque colonne  |
| `.columns`         | Liste les noms des colonnes                      |
| `.index`           | Retourne les index (étiquettes de lignes)        |
| `.sample()`        | Retourne un échantillon aléatoire                |

### Nettoyage des données

| Méthode               | Description                                         |
|-----------------------|-----------------------------------------------------|
| `.isna()`             | Détecte les valeurs manquantes (`isnull()` est un alias) |
| `.notnull()`          | Détecte les valeurs non manquantes                  |
| `.dropna()`           | Supprime les valeurs manquantes                     |
| `.fillna()`           | Remplit les valeurs manquantes                      |
| `.astype()`           | Convertit les types de données                      |
| `.replace()`          | Remplace des valeurs                                |
| `.duplicated()`       | Vérifie les lignes dupliquées                       |
| `.drop_duplicates()`  | Supprime les doublons                               |

### Manipulation des données

| Méthode              | Description                                          |
|----------------------|------------------------------------------------------|
| `.sort_values()`     | Trie selon les valeurs                               |
| `.sort_index()`      | Trie selon les index                                 |
| `.rename()`          | Renomme les axes                                     |
| `.apply()`           | Applique une fonction                                |
| `.map()`             | Applique une correspondance (Series uniquement)      |
| `.applymap()`        | Applique une fonction élément par élément (DataFrame)|
| `.assign()`          | Attribue de nouvelles colonnes                       |
| `.query()`           | Interroge les données avec une expression            |

### Agrégation et Groupement

| Méthode             | Description                                         |
|---------------------|-----------------------------------------------------|
| `.groupby()`        | Regroupe les données pour agrégation                |
| `.agg()`            | Agrège avec une ou plusieurs fonctions              |
| `.mean()`           | Calcule la moyenne                                  |
| `.sum()`            | Calcule la somme                                    |
| `.count()`          | Compte les valeurs non nulles                       |
| `.min()` / `.max()` | Valeurs minimales et maximales                      |
| `.value_counts()`   | Compte les valeurs uniques (Series uniquement)      |

### Fusion et Jointure

| Méthode             | Description                                          |
|---------------------|------------------------------------------------------|
| `pd.merge()`        | Fusionne horizontalement des DataFrames              |
| `.join()`           | Joint des colonnes avec un autre DataFrame           |
| `pd.concat()`       | Concatène selon un axe particulier                   |
| `.append()`         | Ajoute des lignes (obsolète depuis la version 2.0+)  |

### Restructuration

| Méthode              | Description                                         |
|----------------------|-----------------------------------------------------|
| `.pivot()`           | Restructure les données selon les valeurs de colonnes |
| `.pivot_table()`     | Crée un tableau croisé avec agrégation              |
| `.melt()`            | Dépivote les colonnes en lignes                     |
| `.stack()`           | Empile les colonnes dans l’index                    |
| `.unstack()`         | Désempile l’index en colonnes                       |
| `.transpose()`       | Transpose lignes et colonnes                        |
| `.T`                 | Raccourci pour transposition                        |

### Méthodes Statistiques

| Méthode              | Description                                      |
|----------------------|--------------------------------------------------|
| `.mean()`            | Moyenne arithmétique                             |
| `.median()`          | Valeur médiane                                   |
| `.mode()`            | Valeur la plus fréquente                         |
| `.std()`             | Écart-type                                       |
| `.var()`             | Variance                                         |
| `.corr()`            | Matrice de corrélation                           |
| `.cov()`             | Matrice de covariance                            |

---

## Méthodes NumPy

### Création de tableaux

| Méthode               | Description                                          |
|-----------------------|------------------------------------------------------|
| `np.array()`          | Crée un tableau à partir d’une liste ou d’un tuple  |
| `np.zeros()`          | Crée un tableau de zéros                             |
| `np.ones()`           | Crée un tableau de uns                               |
| `np.full()`           | Crée un tableau avec une valeur constante            |
| `np.arange()`         | Crée un tableau avec valeurs espacées régulièrement  |
| `np.linspace()`       | Crée un tableau avec un nombre fixe de valeurs       |
| `np.eye()`            | Matrice identité                                     |
| `np.random.rand()`    | Valeurs aléatoires (distribution uniforme)           |
| `np.random.randn()`   | Valeurs aléatoires (distribution normale)            |
| `np.random.randint()` | Entiers aléatoires dans un intervalle                |

### Manipulation de tableaux

| Méthode               | Description                                         |
|-----------------------|-----------------------------------------------------|
| `.reshape()`          | Change la forme sans modifier les données           |
| `.ravel()`            | Aplati le tableau (vue)                             |
| `.flatten()`          | Aplati le tableau (copie)                           |
| `.transpose()`        | Permute les dimensions                              |
| `.T`                  | Raccourci pour transposition                        |
| `.concatenate()`      | Concatène une séquence de tableaux                  |
| `.stack()`            | Empile les tableaux verticalement ou horizontalement|
| `.hstack()` / `.vstack()` | Empilement horizontal / vertical               |
| `.split()`            | Divise un tableau en plusieurs sous-tableaux        |

### Fonctions Mathématiques

| Méthode               | Description                                         |
|-----------------------|-----------------------------------------------------|
| `np.add()`            | Addition élément par élément                        |
| `np.subtract()`       | Soustraction élément par élément                    |
| `np.multiply()`       | Multiplication élément par élément                  |
| `np.divide()`         | Division élément par élément                        |
| `np.power()`          | Puissance élément par élément                       |
| `np.sqrt()`           | Racine carrée                                       |
| `np.exp()`            | Exponentielle                                       |
| `np.log()`            | Logarithme naturel                                  |
| `np.abs()`            | Valeur absolue                                      |

### Fonctions Statistiques

| Méthode               | Description                                        |
|-----------------------|----------------------------------------------------|
| `np.mean()`           | Moyenne des éléments                              |
| `np.median()`         | Valeur médiane                                    |
| `np.std()`            | Écart-type                                        |
| `np.var()`            | Variance                                          |
| `np.min()` / `np.max()` | Valeurs minimale et maximale                    |
| `np.percentile()`     | Valeur du percentile                              |
| `np.corrcoef()`       | Coefficients de corrélation                       |

### Algèbre Linéaire

| Méthode               | Description                                          |
|-----------------------|------------------------------------------------------|
| `np.dot()`            | Produit scalaire de deux tableaux                    |
| `np.matmul()`         | Multiplication matricielle                           |
| `np.linalg.inv()`     | Inverse d’une matrice                                |
| `np.linalg.det()`     | Déterminant d’une matrice                            |
| `np.linalg.eig()`     | Valeurs propres et vecteurs propres                  |
| `np.linalg.norm()`    | Norme d’un vecteur ou d’une matrice                  |

---

**Vous pouvez vous rediriger vers le CheatSheet [Méthodes de data Preprocessing](Data_Preprocessing_Methods_FR.ipynb)**

_Edité: 22/04/2025_