---
layout: TheoryContentLayout
kicker: Tableaux croisés dynamiques
title: Penser le TCD
slide_info: false
---

Partir de la question avant de déplacer les champs.

| Question | Zone |
|---|---|
| Regrouper / comparer ? | `Lignes` / `Colonnes` |
| Calculer quoi ? | `Valeurs` |
| Isoler quoi ? | `Filtres` |

Exemples :

- Chiffre d'affaires par `Produit` et par `Mois`
- Analyse limitée par `Canal`

<TheDownload label="Télécharger l'exemple" href="example-tcd.xlsx" />

<!--
À retenir : un TCD n'est pas d'abord une manipulation Excel. C'est une traduction d'une question métier en structure d'analyse.

Mémo :

- ce que l'on veut regrouper ou comparer va dans `Lignes` ou `Colonnes` ;
- ce que l'on veut compter, sommer ou moyenner va dans `Valeurs` ;
- ce que l'on veut isoler ou limiter va dans `Filtres`.

Exemple : "Quel chiffre d'affaires avons-nous réalisé par produit et par mois ?"

- `Produit` sert à regrouper les ventes en `Lignes`.
- `Mois` sert à comparer les périodes en `Colonnes`.
- `Chiffre_affaires` va dans `Valeurs` avec l'opération `Somme`.
- `Canal` va dans `Filtres` pour isoler les ventes en magasin, web ou partenaire.

Tip : en changeant les champs de zone, on ne change pas seulement l'affichage. On change la question à laquelle répond le TCD.

Démo :

- créer un TCD à partir de la source ;
- déplacer un champ entre `Lignes` et `Colonnes` ;
- montrer la différence de lecture entre lignes et colonnes ;
- passer un champ dans `Valeurs` ;
- utiliser un filtre ;
- montrer éventuellement un segment comme représentation visuelle d'un filtre ;
- faire remarquer que chaque déplacement de champ modifie immédiatement la question analysée.
-->
