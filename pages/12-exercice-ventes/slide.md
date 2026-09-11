---
layout: ExerciseLayout
kicker: Exercice
title: Suivi simple de ventes
duration: 15 à 20 min
durationLabel: durée estimée
slide_info: false
---

Créer un tableau de ventes mensuelles, calculer les indicateurs principaux, puis produire un libellé exploitable.

<TheDownload label="Télécharger l'exercice" href="./exercice-ventes.zip" />

**Étape 1** - Calculs :

- Une colonne `Total` avec `Quantité * Prix unitaire`.
- Le total général, la moyenne, le minimum, le maximum et le nombre de valeurs.

**Étape 2** - Texte :

- Une colonne `Libellé` avec `CONCAT(Produit;" - ";Mois;" - ";Canal)`.
- Un titre clair pour chaque colonne.
- Une mise en forme simple : titres visibles, euros, colonnes ajustées.

<TheFold title="Données d'exemple" :open="false">

| Mois | Produit | Canal | Quantité | Prix unitaire |
|---|---|---|---:|---:|
| Janvier | Sandwich | Boutique | 44 | 35 |
| Février | Sandwich | Livraison | 23 | 21 |
| Mars | Salade | Boutique | 35 | 25 |
| Avril | Salade | Livraison | 56 | 32 |
| Mai | Sandwich | Boutique | 234 | 14 |
| Juin | Salade | Boutique | 55 | 19 |
| Juillet | Sandwich | Livraison | 13 | 40 |

</TheFold>
