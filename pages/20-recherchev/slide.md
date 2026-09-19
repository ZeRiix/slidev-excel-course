---
layout: VisualContentLayout
kicker: Recherche de données
title: RECHERCHEV
placeholder: "Mini-capture Excel avec un catalogue à gauche, une commande à compléter à droite, et la colonne `Code produit` mise en évidence."
slide_info: false
image: ./image.png
---

`RECHERCHEV` cherche une valeur dans la première colonne d'un tableau.

Elle renvoie ensuite une information située sur la même ligne.

<div class="h-5"/>

**Exemple:**

```excel {all|2|3|4|5}
=RECHERCHEV(
  A10;         // valeur cherchée
  Catalogue;   // table de référence
  2;           // numéro colonne dans la table
  FAUX         // correspondance exacte
)
```

<!--
À retenir : `RECHERCHEV` cherche la valeur dans la première colonne de la table et ne peut renvoyer qu'une information située à sa droite.

Tip : pour rechercher un code, un identifiant ou une référence, utilisez généralement `FAUX` afin d'imposer une correspondance exacte.
-->
