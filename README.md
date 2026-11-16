## Graph_Mining_Reddit
# Data
On a un .tsv avec commes variables :
SOURCE_SUBREDDIT : le nom du subreddit
TARGET_SUBREDDIT : le thème du subreddit
POST_ID : ID unique du post            
TIMESTAMP : la date du post
LINK_SENTIMENT : -1 ou 1                                          
La collone properties mérite une description à part

## Description de la colonne `properties`

La colonne `properties` contient un vecteur de **86 caractéristiques numériques** (séparées par des virgules) représentant la signature topologique et statistique globale de chaque graphe.

### Structure du vecteur (86 valeurs)

Le vecteur est divisé en trois blocs principaux :

1. **Dimensions et statistiques de base (Indices `0` à `17`)**
   * **Volumétrie :** Nombre total d'arêtes (E), nombre d'arêtes uniques, et nombre total de nœuds (V).
   * **Ratios structurels :** Proportions d'arêtes et de nœuds vérifiant certaines propriétés topologiques (ex. : taille de la plus grande composante connexe, arêtes réciproques ou boucles).
   * **Métriques de connectivité :** Degré moyen, degré maximum, diamètre du graphe et indicateurs booléens (ex. : graphe connexe).

2. **Indices topologiques globaux (Indices `18` à `20`)**
   * Trois métriques normalisées (comprises entre `0` et `1`) mesurant la structure globale du réseau, telles que la **densité du graphe**, le **coefficient de clustering moyen** (transitivité) et la **modularité / assortativité**.

3. **Distributions normalisées / Histogrammes (Indices `21` à `85`)**
   * Concaténation de **deux distributions de probabilité** (histogrammes normal)
