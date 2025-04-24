# Lexique Python et Pandas
**Auteur:** Gaspard-Fauvelle Angel  
**License:** [CC BY-NC-SA 2.0](https://creativecommons.org/licenses/by-nc-sa/2.0/)  

Here is the english version of the document [Python & Pandas CheatSheet](./Python_Pandas_CheatSheet_Eng.md)

## Table des matières
- [I. Introduction aux types de données et variables](#I.-Introduction-aux-types-de-données-et-variables)
    - [1.2. Types de données (Types scalaires)](#1.2.-Types-de-données-(Types-scalaires))
- [Ⅱ. Fonctions intégrées Python](#Ⅱ.-Fonctions-intégrées-Python)
- [III. Concatenation, opérations arithmétiques & Comparaisons](#III.-Concaténation,-opérations-arithmétiques-&-comparaisons)
    - [3.1. Concatenations](#3.1.-Concatenations)
- [Ⅳ. Introduction aux structures de données (Types de données abstraits)](#Ⅳ.-Introduction-aux-structures-de-données-(Types-de-données-abstraits))
    - [4.1. Séquences et structures de données de collection (Type de données vectorielles / bidimensionnelles)](#4.1.-Séquences-et-structures-de-données-de-collection-(Types-de-données-vectorielles-/-bidimensionnelles))
    - [4.2. Différence entre la built-in `list[]` de Python et le built-in `array([])` de NumPy](#4.2.-Différence-entre-la-built-in-list[]-de-Python-et-le-built-in-array([])-de-NumPy)



---

## I. Introduction aux types de données et variables  
### 1.2. Types de données (Types scalaires)

| **Catégorie**      | **Type**                         | **Description**                                                       | **Exemples**                                   |
|--------------------|----------------------------------|-----------------------------------------------------------------------|------------------------------------------------|
| Types numériques   | `int` (Entiers)                  | Entier signé de précision arbitraire.                                  | `42`, `-7`, `0`, `123456789`, `-999`           |
|                    | `float` (Nombres décimaux)       | Nombre à virgule flottante de double précision.                        | `3.14`, `-0.001`, `0.0`, `2.71828`, `-300.0`   |
|                    | `complex` (Nombres imaginaires)  | Nombre complexe de deux flottants (partie réelle et imaginaire).       | `1+2j`, `-3+4j`, `0+0j`, `3-1j`, `-2+5j`      |
| Type Booléen       | `bool` (Booléens)                | Booléen (un sous-type de `int` : `True` == 1, `False` == 0).           | `True`, `False`                                |
| Type spécial       | `NoneType`                       | Type de la valeur spéciale `None`, représentant l'absence de valeur.  | `None`                                         |
| Type séquence      | `str` (Chaînes de caractères)    | Chaîne de caractères Unicode de longueur variable.                     | `"Bonjour"`, `"Python 3.10"`, `"30"`, `"Hello, world!"`, `"Café"` |
|                    | `object`, `category`             | Types spécifiques à Pandas : `object` pour les types mixtes, `category` pour les données catégorielles. | valeurs mixtes, codes catégoriels |

_Les types de données primitifs sont les éléments de base d'un langage de programmation :_  
- Ce sont les plus petites unités d'information que vous pouvez utiliser pour construire des constructions plus complexes dans votre code.  
- Ils ne peuvent pas être décomposés en parties plus petites.

_Ces types fournissent les ingrédients essentiels pour effectuer des calculs, stocker du texte, prendre des décisions, et plus encore. Tout ce qui est plus complexe dans votre programme est construit à partir de ces éléments de base._

> Dans Jupyter, appuyez sur **Shift + Enter** pour exécuter une cellule.

---

## Ⅱ. Fonctions intégrées Python

| **Catégorie**  | **Fonction** | **Description**                                              | **Exemples**                            |
|----------------|--------------|--------------------------------------------------------------|-----------------------------------------|
| **Retourne**   | `len()`      | Retourne la longueur d'un objet (liste, chaîne, etc.).       | `len([1, 2, 3])` retourne `3`          |
|                | `type()`     | Retourne le type de l'objet donné.                           | `type(42)` retourne `<class 'int'>`    |
|                | `sum()`      | Retourne la somme d'un itérable de nombres.                  | `sum([1, 2, 3])` retourne `6`          |
|                | `min()`      | Retourne l'élément le plus petit d'un itérable.              | `min([1, 2, 3])` retourne `1`          |
|                | `max()`      | Retourne l'élément le plus grand d'un itérable.              | `max([1, 2, 3])` retourne `3`          |
|                | `abs()`      | Retourne la valeur absolue d'un nombre.                      | `abs(-7)` retourne `7`                 |
|                | `round()`    | Arrondit un nombre à virgule flottante à un nombre spécifié de décimales. | `round(3.14159, 2)` retourne `3.14`   |
|                | `sorted()`   | Retourne une nouvelle liste triée à partir de l'itérable donné. | `sorted([3, 1, 2])` retourne `[1, 2, 3]` |
| **Crée**       | `range()`    | Génère une séquence d'entiers (pour les boucles `for`).      | `range(5)` → `[0, 1, 2, 3, 4]`         |
|                | `list()`     | Crée/convertit une liste à partir d'un itérable.             | `list("abc")` retourne `['a','b','c']` |
|                | `set()`      | Crée/convertit un ensemble à partir d'un itérable, supprimant les doublons. | `set([1,2,2,3])` retourne `{1,2,3}` |
|                | `dict()`     | Crée/convertit un dictionnaire à partir d'un itérable de paires clé-valeur. | `dict([("a",1),("b",2)])` retourne `{'a':1,'b':2}` |
|                | `zip()`      | Combine des itérables élément par élément en tuples.         | `zip([1,2,3],["a","b","c"])` → `[(1,'a'),(2,'b'),(3,'c')]` |
| **Convertit**  | `str()`      | Convertit un objet en chaîne de caractères.                  | `str(42)` retourne `"42"`              |
|                | `int()`      | Convertit une chaîne ou un nombre flottant en entier.        | `int("42")` retourne `42`              |
|                | `float()`    | Convertit une chaîne ou un entier en nombre flottant.        | `float("3.14")` retourne `3.14`        |
| **Autres**     | `print()`    | Affiche des messages à l'écran ou dans la console.           | `print("Hello")` affiche `Hello`       |
|                | `input()`    | Lit une ligne de texte depuis l'entrée standard (clavier).   | `name = input("Enter name: ")`         |

_Les fonctions intégrées de Python vous permettent d'effectuer des tâches courantes sans importer de bibliothèques supplémentaires._  
_En savoir plus : [Liste complète des fonctions intégrées](https://docs.python.org/3/library/functions.html)._

---

## III. Concaténation, opérations arithmétiques & comparaisons

| **Catégorie**              | **Opérateur**        | **Symbole** | **Description**                                              | **Exemple**              | **Détail**                    | **Résultat**    |
|----------------------------|----------------------|-------------|--------------------------------------------------------------|---------------------------|-------------------------------|-----------------|
| Opérations Arithmétiques   | Addition             | `+`         | Additionne deux nombres.                                     | `5 + 3`                   | `5 + 3`                       | `8`             |
|                            | Soustraction         | `-`         | Soustrait un nombre à un autre.                              | `5 - 3`                   | `5 - 3`                       | `2`             |
|                            | Multiplication       | `*`         | Multiplie deux nombres.                                      | `3 * 5`                   | `5 + 5 + 5`                   | `15`            |
|                            | Division             | `/`         | Divise un nombre par un autre.                               | `6 / 3`                   | `6 ÷ 3 = 2`                   | `2.0`           |
|                            | Division entière     | `//`        | Renvoie le quotient entier d'une division.                   | `7 // 3`                  | `7 ÷ 3 = 2`                   | `2`             |
|                            | Modulo               | `%`         | Reste de la division.                                        | `7 % 3`                   | `7 - (3 * 2) = 1`             | `1`             |
|                            | Exponentiation       | `**`        | Élève un nombre à la puissance d’un autre.                   | `2 ** 3`                  | `2 * 2 * 2 = 8`               | `8`             |
| Opérateurs de comparaison  | Égal à               | `==`        | Vérifie l’égalité.                                           | `5 == 5`                  | Est-ce que 5 = 5 ?            | `True`          |
|                            | Différent de         | `!=`        | Vérifie l’inégalité.                                         | `5 != 3`                  | Est-ce que 5 ≠ 3 ?            | `True`          |
|                            | Supérieur à          | `>`         | Vérifie si l'opérande gauche est plus grand.                 | `5 > 3`                   | Est-ce que 5 > 3 ?            | `True`          |
|                            | Inférieur à          | `<`         | Vérifie si l'opérande gauche est plus petit.                 | `3 < 5`                   | Est-ce que 3 < 5 ?            | `True`          |
|                            | Supérieur ou égal    | `>=`        | Vérifie la relation ≥.                                       | `5 >= 5`                  | Est-ce que 5 ≥ 5 ?            | `True`          |
|                            | Inférieur ou égal    | `<=`        | Vérifie la relation ≤.                                       | `3 <= 5`                  | Est-ce que 3 ≤ 5 ?            | `True`          |
|                            | Identité (est)       | `is`        | Vérifie si les deux objets pointent vers la même référence.  | `a is b`                  | Même objet en mémoire ?       | `True/False`    |
|                            | Identité (n’est pas) | `is not`    | Vérifie si les objets sont différents.                       | `a is not b`              | Objets différents ?           | `True/False`    |
|                            | Appartenance         | `in`        | Vérifie l’appartenance à une séquence.                       | `'a' in 'apple'`          | `'a'` dans `"apple"` ?        | `True`          |
|                            | Non-appartenance     | `not in`    | Vérifie l’absence dans une séquence.                         | `'b' not in 'apple'`      | `'b'` pas dans `"apple"` ?    | `True`          |
| Opérations Logiques        | ET                   | `and`       | Renvoie `True` si les deux sont `True`.                      | `True and False`          | Les deux sont vrais ?         | `False`         |
|                            | OU                   | `or`        | Renvoie `True` si au moins un est `True`.                    | `True or False`           | L’un est vrai ?               | `True`          |
|                            | NON                  | `not`       | Renvoie `True` si l’opérande est `False`.                    | `not True`                | Pas vrai ?                    | `False`         |
|                            | NAND                 | `not (a and b)` | `True` si les deux ne sont pas `True`.                    | `not (True and False)`    | Les deux ne sont pas vrais ?  | `True`          |
|                            | NOR                  | `not (a or b)`  | `True` si aucun n’est `True`.                           | `not (True or False)`     | Aucun n’est vrai ?            | `False`         |
|                            | XOR                  | `a != b`    | `True` si les opérandes sont différents.                     | `True != False`           | Différents ?                  | `True`          |
|                            | XNOR                 | `not (a != b)`| `True` si les opérandes sont identiques.                 | `not (True != False)`     | Identiques ?                  | `False`         |

#### 3.1. Concatenations

La concaténation permet la jointure d'une ou plusieurs strings.  
Nous utilisons `+` afin de joindre plusieurs strings:

```python
variable1 = "Salut"
variable2 = "Comment allez‑vous ?"
print(variable1 + ' ' + variable2)  # Salut Comment allez‑vous ?
print(variable2 + ' ' + variable1)  # Comment allez‑vous ? Salut
```

---

## Ⅳ. Introduction aux structures de données (Types de données abstraits)

### 4.1. Séquences et structures de données de collection (Types de données vectorielles / bidimensionnelles)

On peut également stocker d'autres types d'objets en tant que variables, comme les vecteurs ou les variables unidimensionnelles :

| **Catégorie**   | **Structure de données** | **Description**                                                                                          | **Exemples**                                                        |
|-----------------|--------------------------|----------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------|
| Séquence        | list (liste)             | Séquence ordonnée et mutable pouvant contenir des éléments de types variés.                             | [1, 2, 3], ["pomme", "banane", "cerise"], [42, "bonjour", True]     |
|                 | tuple                    | Séquence ordonnée et immuable, utilisée pour regrouper des éléments qui ne doivent pas être modifiés.   | (1, 2, 3), ("rouge", "vert", "bleu"), ("a", 42, False)              |
|                 | range                    | Séquence immuable représentant une progression arithmétique, souvent utilisée dans les boucles.         | range(5), range(1, 10), range(0, 20, 2)                             |
| Collection       | set (ensemble)           | Collection non ordonnée, mutable, contenant uniquement des éléments uniques.                            | {1, 2, 3}, {"chat", "chien", "oiseau"}, {10, 20, 30}                |
|                 | frozenset                | Version immuable d’un set, utile lorsque la collection d’éléments uniques ne doit pas être modifiée.    | frozenset({1, 2, 3}), frozenset({"a", "b", "c"})                    |
| Dictionnaire     | dict (dictionnaire)      | Collection de paires clé-valeur avec des clés uniques. L’ordre d’insertion est conservé depuis Python 3.7. | {"nom": "Alice", "âge": 30}, {1: "un", 2: "deux", 3: "trois"}       |

| **Caractéristique**           | **Séquences**                   | **Collections**                 | **Dictionnaires**                         |
|-------------------------------|----------------------------------|----------------------------------|-------------------------------------------|
| Ordonné                       | ✔ (list, tuple, range)          | ✖ (set, frozenset non ordonnés) | ✔ (Ordonné depuis Python 3.7)             |
| Mutable                       | ✔ (list, array)                 | ✔ (set)                         | ✔ (dict)                                  |
| Immuable                      | ✔ (tuple, range)                | ✔ (frozenset)                   | ✖                                         |
| Autorise les doublons         | ✔                                | ✖ (set, frozenset)              | ✖ (clés uniques, valeurs peuvent doubler) |
| Paires clé-valeur             | ✖                                | ✖                               | ✔                                         |
| Types hétérogènes             | ✔ (list, tuple)                 | ✔ (set)                         | ✔ (dict)                                  |
| Types homogènes uniquement    | ✔ (array)                       | ✖                               | ✖                                         |
| Test d'appartenance rapide    | ✖                                | ✔ (set, frozenset)              | ✔ (par les clés)                          |
| Itérable                      | ✔                                | ✔                               | ✔                                         |
| Indexable                     | ✔ (list, tuple, range)          | ✖                               | ✔ (par les clés)                          |

### **Explications supplémentaires** :
- **Ordonné** : `list`, `tuple`, `range`, et `dict` (depuis Python 3.7) conservent l’ordre des éléments, contrairement à `set` et `frozenset`.
- **Mutable vs Immuable** : `list` et `dict` sont modifiables, tandis que `tuple`, `range` et `frozenset` sont immuables.
- **Doublons** : `set`, `frozenset` et les clés de `dict` n’autorisent pas les doublons, garantissant l’unicité.
- **Paires clé-valeur** : Caractéristique exclusive aux dictionnaires (`dict`).
- **Types homogènes** : Obligatoires dans les `array` (types stricts, ex : que des `int` ou `float`).
- **Test d'appartenance** : Très performant avec `set`, `frozenset` et `dict` (via les clés).

[🔗 Méthodes des listes/arrays](https://www.w3schools.com/python/python_ref_list.asp) | [🔗 Méthodes des tuples](https://www.w3schools.com/python/python_ref_tuple.asp) |
[🔗 Méthodes des ensembles](https://www.w3schools.com/python/python_ref_set.asp) | [🔗 Méthodes des dictionnaires](https://www.w3schools.com/python/python_ref_dictionary.asp) | [🔗 Mots-clés Python](https://www.w3schools.com/python/python_ref_keywords.asp)

---

### 4.2. Différence entre la built-in `list[]` de Python et le built-in `array([])` de NumPy

| **Caractéristique**     | **Array (tableau)**                                                                            | **List (liste)**                                                     |
|-------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| **Type des éléments**   | Doit contenir uniquement des éléments du même type.                                           | Peut contenir des éléments de types différents (int, str, etc.).     |
| **Performances**        | Plus compact et rapide pour les opérations sur des types homogènes (int, float, etc.).        | Plus généraliste, mais légèrement moins performant.                  |
| **Compatibilité**       | Nécessite le module `array` ou une bibliothèque comme NumPy.                                  | Type intégré, toujours disponible.                                   |
| **Exemple**             | `array('i', [1, 2, 3])` (entiers uniquement).                                                  | `[1, "a", 3.5, True]` (types mixtes autorisés).                      |

---

**Vous pouvez maintenant vous rediriger vers la CheatSheet de [NumPy/Pandas](./NumPy_Pandas_CheatSheet_FR.md)**

_Edité: 22/04/2025_