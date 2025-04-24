# 📘 SQL Cheat Sheet
**Auteur:** Gaspard-Fauvelle Angel  
**License:** [CC BY-NC-SA 2.0](https://creativecommons.org/licenses/by-nc-sa/2.0/)  

## Sommaire
- [🧩 CRUD (Manipulation de Données)](#🧩-CRUD-(Manipulation-de-Données))
- [🔎 Clause de filtre et ses opérateurs](#🔎-Clause-de-filtre-et-ses-opérateurs)
- [Clause de Tri et ses options](#Clause-de-Tri-et-ses-options)
- [Clause de groupement et son filtre](#Clause-de-groupement-et-son-filtre)
- [🧰 Autres Clauses Utiles](#🧰-Autres-Clauses-Utiles)
- [Fonctions d'Agrégation](#Fonctions-d'Agrégation)
- [Jointures](#Jointures)
- [Fonctions DDL (Data Definition Language)](#Fonctions-DDL-(Data-Definition-Language))
- [🔐 DCL (Data Control Language)](#🔐-DCL-(Data-Control-Language))
- [🔐 Contraintes](#🔐-Contraintes)
- [🔁 Transactions](#🔁-Transactions)

---

### 🧩 CRUD (Manipulation de Données)
| **Clauses**   | **Catégorie**    | **Description**                                                              |
|--------------|------------------|------------------------------------------------------------------------------|
| `SELECT`     | Lecture          | Récupère des données d'une ou plusieurs tables.                             |
| `INSERT INTO`| Création         | Ajoute de nouvelles lignes de données dans une table.                       |
| `UPDATE`     | Modification     | Modifie les données existantes dans une ou plusieurs lignes d'une table.    |
| `DELETE FROM`| Suppression      | Supprime des lignes de données d'une table.                                 |

---

### 🔎 Clause de filtre et ses opérateurs
| **Clause/Opérateur** | **Catégorie** | **Description**                                                          |
|----------------------|---------------|--------------------------------------------------------------------------|
| `WHERE`              | Filtre        | Spécifie une condition pour filtrer les lignes retournées.              |
| `AND`                | Opérateur     | Combine plusieurs conditions, toutes doivent être vraies.               |
| `OR`                 | Opérateur     | Combine plusieurs conditions, au moins une doit être vraie.             |
| `NOT`                | Opérateur     | Inverse le résultat d'une condition.                                    |
| `IN`                 | Opérateur     | Vérifie si une valeur est dans une liste.                               |
| `BETWEEN`            | Opérateur     | Sélectionne une plage de valeurs.                                       |
| `LIKE`               | Opérateur     | Recherche par motif (avec `%`, `_`).                                    |
| `IS NULL`            | Opérateur     | Vérifie si une valeur est `NULL`.                                       |
| `IS NOT NULL`        | Opérateur     | Vérifie si une valeur est non `NULL`.                                   |
| `EXISTS`             | Opérateur     | Vérifie l'existence de lignes dans une sous-requête.                    |
| `NOT EXISTS`         | Opérateur     | Vérifie la non existence de lignes dans une sous-requête.               |

---

### Clause de Tri et ses options
| **Clause/Option** | **Catégorie** | **Description**                                      |
|------------------|---------------|------------------------------------------------------|
| `ORDER BY`       | Tri           | Trie les résultats par une ou plusieurs colonnes.   |
| `ASC`            | Option        | Ordre croissant (par défaut).                       |
| `DESC`           | Option        | Ordre décroissant.                                  |

---

### Clause de groupement et son filtre
| **Clause** | **Catégorie** | **Description**                                    |
|------------|---------------|----------------------------------------------------|
| `GROUP BY` | Groupement    | Regroupe les lignes ayant les mêmes valeurs.       |
| `HAVING`   | Filtre        | Filtre les groupes créés avec `GROUP BY`.          |

---

### 🧰 Autres Clauses Utiles
| **Clause**               | **Catégorie** | **Description**                                              |
|--------------------------|---------------|--------------------------------------------------------------|
| `LIMIT` / `TOP`          | Limitation    | Limite le nombre de résultats.                              |
| `OFFSET` / `FETCH NEXT`  | Pagination    | Ignore un certain nombre de résultats.                      |
| `AS`                     | Alias         | Renomme durant la requête une table ou colonne.             |
| `DISTINCT`               | Sélection     | Élimine les doublons.                                       |
| `UNION`                  | Combinaison   | Combine plusieurs requêtes en supprimant les doublons.      |
| `UNION ALL`              | Combinaison   | Combine plusieurs requêtes en gardant les doublons.         |
| `VIEW`                   | Objet         | Crée une vue virtuelle.                                     |
| `PROCEDURE` / `FUNCTION` | Objet         | Crée une procédure ou une fonction stockée.                 |

---

### Fonctions d'Agrégation
| **Fonction** | **Catégorie** | **Description**                |
|-------------|----------------|--------------------------------|
| `COUNT()`   | Agrégation     | Nombre de lignes.              |
| `SUM()`     | Agrégation     | Somme des valeurs numériques.  |
| `AVG()`     | Agrégation     | Moyenne des valeurs.           |
| `MIN()`     | Agrégation     | Valeur minimale.               |
| `MAX()`     | Agrégation     | Valeur maximale.               |

---

### Jointures
| **Jointure**      | **Catégorie** | **Description**                                                                 |
|------------------|----------------|----------------------------------------------------------------------------------|
| `JOIN`           | Jointure       | Combine les lignes de plusieurs tables.                                         |
| `INNER JOIN`     | Jointure       | Retourne les lignes avec correspondance dans les deux tables.                  |
| `LEFT JOIN`      | Jointure       | Toutes les lignes de gauche + correspondances à droite.                        |
| `RIGHT JOIN`     | Jointure       | Toutes les lignes de droite + correspondances à gauche.                        |
| `FULL OUTER JOIN`| Jointure       | Toutes les lignes de gauche et de droite (avec ou sans correspondance).        |
| `CROSS JOIN`     | Jointure       | Produit cartésien de deux tables.                                              |

---

### Fonctions DDL (Data Definition Language)
| **Commande**       | **Catégorie** | **Description**                                      |
|--------------------|---------------|------------------------------------------------------|
| `CREATE TABLE`     | DDL           | Crée une nouvelle table.                            |
| `ALTER TABLE`      | DDL           | Modifie la structure d'une table.                   |
| `DROP TABLE`       | DDL           | Supprime une table.                                 |
| `CREATE DATABASE`  | DDL           | Crée une nouvelle base de données.                  |
| `ALTER DATABASE`   | DDL           | Modifie une base de données.                        |
| `DROP DATABASE`    | DDL           | Supprime une base de données.                       |
| `CREATE INDEX`     | DDL           | Crée un index pour accélérer les recherches.        |
| `DROP INDEX`       | DDL           | Supprime un index.                                  |

---

### 🔐 DCL (Data Control Language)
| **Commande** | **Catégorie** | **Description**                                  |
|-------------|---------------|--------------------------------------------------|
| `GRANT`     | DCL           | Accorde des privilèges à un utilisateur ou rôle. |
| `REVOKE`    | DCL           | Révoque des privilèges.                          |

---

### 🔐 Contraintes
| **Contrainte** | **Catégorie** | **Description**                         |
|----------------|---------------|-----------------------------------------|
| `PRIMARY KEY`  | Contrainte    | Identifie l'unicité d'une ligne.        |
| `FOREIGN KEY`  | Contrainte    | Lien entre deux tables.                 |
| `UNIQUE`       | Contrainte    | Toutes les valeurs doivent être uniques.|
| `NOT NULL`     | Contrainte    | Empêche les valeurs `NULL`.             |
| `CHECK`        | Contrainte    | Imposent des conditions sur les valeurs.|
| `DEFAULT`      | Contrainte    | Définit une valeur par défaut.          |

---

### 🔁 Transactions
| **Commande**         | **Catégorie** | **Description**                                                              |
|----------------------|---------------|------------------------------------------------------------------------------|
| `START TRANSACTION`  | Transaction   | Démarre une transaction.                                                    |
| `COMMIT`             | Transaction   | Valide la transaction.                                                      |
| `ROLLBACK`           | Transaction   | Annule la transaction.                                                      |
| `SAVEPOINT`          | Transaction   | Point de sauvegarde partiel.                                                |
| `TRUNCATE`           | Transaction   | Suppression des données et métadonnées de la table sans possibilité de rollback. |

---

_Edité: 22/04/2025_