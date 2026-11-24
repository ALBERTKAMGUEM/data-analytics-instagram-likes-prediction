 Prédiction des likes Instagram avec le Machine Learning

 Présentation du projet

Ce projet a pour objectif d'analyser les facteurs qui influencent le nombre de likes obtenus par une publication Instagram et de construire des modèles de Machine Learning capables de prédire l'engagement des utilisateurs.


 Objectifs

- Explorer et comprendre les données des publications Instagram.
- Étudier la relation entre le nombre d'abonnés et le nombre de likes.
- Préparer et transformer les données pour le Machine Learning.
- Construire deux modèles de régression linéaire.
- Évaluer leurs performances avec des métriques adaptées.
- Étudier l'intérêt de l'engagement historique pour améliorer les prédictions.

 Technologies utilisées

| Python | Analyse et modélisation |
| Pandas | Manipulation et nettoyage des données |
| Plotly Express | Visualisation interactive |
| Scikit-learn | Machine Learning |
| NumPy | Calcul numérique |
| Jupyter Notebook | Développement et expérimentation |
| Git & GitHub | Versionnement et partage |

Exploration des données

Le jeu de données contient plusieurs informations relatives aux publications Instagram.

| Variable | Description |
|---|---|
| `id` | Identifiant de l'auteur |
| `followers` | Nombre d'abonnés |
| `comments` | Nombre de commentaires |
| `posts` | Nombre de publications |
| `likes` | Nombre de likes |
| `ts` | Date et heure de publication |

Préparation des données

Les principales opérations réalisées sont :

1. Chargement du fichier CSV compressé.
2. Identification des auteurs uniques.
3. Tri chronologique des publications.
4. Suppression des doublons pour conserver la publication la plus récente de chaque auteur.
5. Préparation des variables explicatives et de la variable cible.

Analyse exploratoire

Un graphique de dispersion a été réalisé pour étudier la relation entre le nombre d'abonnés et le nombre de likes.


. Modèle 1 — Régression linéaire simple

 Objectif

Prédire le nombre de likes à partir d'une seule variable explicative : le nombre d'abonnés.

Variable explicative (X) :** `followers`

Variable cible (y) :** `likes`

Méthodologie

- Séparation des données : 80 % entraînement et 20 % test.
- Standardisation avec `StandardScaler`.
- Entraînement d'un modèle `LinearRegression`.
- Évaluation sur les données de test.
Évaluation

Trois métriques sont utilisées :

- **R²** : proportion de variance expliquée par le modèle.
- **MSE** : moyenne des erreurs quadratiques.
- **MAE** : moyenne des erreurs absolues.

Ce premier modèle sert de référence pour mesurer l'amélioration apportée par une nouvelle variable.

 Feature Engineering — Engagement historique

 Hypothèse

Les auteurs ayant obtenu davantage de likes sur leurs publications précédentes pourraient obtenir davantage de likes sur leurs futures publications.

Création de `historical_likes`

Une nouvelle variable est construite à partir de la médiane du nombre de likes des publications précédentes de chaque auteur.


 Modèle 2 — Régression linéaire multiple

 Objectif

Améliorer les prédictions en combinant le nombre d'abonnés et l'engagement historique.

**Variables explicatives (X) :
- `followers`
- `historical_likes`

**Variable cible (y) : `likes`

Méthodologie

- Séparation entraînement/test (80 % / 20 %).
- Standardisation des variables explicatives.
- Entraînement d'un second modèle `LinearRegression`.
- Évaluation sur les données de test.

 Comparaison des performances

L'objectif est de déterminer si l'ajout de l'engagement historique améliore la qualité des prédictions.

Un modèle présentant un R² plus élevé et des erreurs MSE et MAE plus faibles sera généralement considéré comme plus performant sur les données évaluées.




 👨‍💻 Auteur

Albert Kamguem


