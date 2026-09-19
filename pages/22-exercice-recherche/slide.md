---
layout: ExerciseLayout
kicker: Exercice
title: Catalogue produits et commandes
duration: 25 min
durationLabel: durée estimée
slide_info: false
---

Nettoyer une liste de commandes importée, puis la compléter automatiquement à partir d'un catalogue produits.

<TheDownload label="Télécharger l'exercice" href="./exercice-recherche.zip" />

**Étape 1** - Préparer les données :

- Nommer la plage du catalogue : `Catalogue`.
- Créer `Code produit` à partir de `Code importé` avec `REMPLACER`.
- Créer `Référence commande` avec `CONCAT(Client;" - ";Code produit)`.

**Étape 2** - Rechercher et contrôler :

- Remplir `Produit`, `Catégorie` et `Prix unitaire` avec `RECHERCHEV`.
- Éviter l'affichage brut de `#N/A` si le code n'existe pas.
- Calculer `Total` avec `Quantité * Prix unitaire` quand le prix existe.
- Bonus : refaire une recherche avec `INDEX` + `EQUIV`.

<TheFold title="Catalogue produits" :open="false">

| Code produit | Produit | Catégorie | Prix unitaire |
|---|---|---|---:|
| P001 | Clavier | Informatique | 8,50 |
| P002 | Disque dur | Informatique | 120,00 |
| P003 | Clé USB | Informatique | 3,43 |
| P004 | DVD-Rom | Stockage | 1,00 |
| P005 | CD-Rom | Stockage | 0,15 |

</TheFold>

<TheFold title="Commandes importées" :open="false">

| Code importé | Client | Quantité | Code produit | Référence commande | Produit | Catégorie | Prix unitaire | Total |
|---|---|---:|---|---|---|---|---:|---:|
| PRD-001 | Martin | 25 |  |  |  |  |  |  |
| PRD-002 | Durand | 56 |  |  |  |  |  |  |
| PRD-003 | Bernard | 300 |  |  |  |  |  |  |
| PRD-004 | Robert | 2500 |  |  |  |  |  |  |
| PRD-999 | Moreau | 12 |  |  |  |  |  |  |

</TheFold>

<TheHint>

Pour éviter d'afficher une erreur brute, envelopper une formule avec `SIERREUR`.

```excel
=SIERREUR(RECHERCHEV(...);"Code inconnu")
```

</TheHint>

<!--
Attention : `SIERREUR` permet de rendre une erreur plus lisible, mais ne doit pas servir à masquer une erreur sans en comprendre la cause.
-->
