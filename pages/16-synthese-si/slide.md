---
layout: VisualContentLayout
kicker: Synthèse
title: NB.SI et SOMME.SI
placeholder: "Capture Excel avec un petit tableau Ville / Client / Montant. À droite, afficher deux résultats : nombre de commandes à Paris et total des montants à Paris. Encadrer la colonne Ville en bleu, la colonne Montant en vert, et les deux cellules de résultat."
imageSide: right
image: ./image.png
slide_info: false
---

Ces deux fonctions permettent de résumer une liste selon un critère.

```excel
=NB.SI(A2:A20;"Paris")
=SOMME.SI(A2:A20;"Paris";C2:C20)
```

- `NB.SI` compte les lignes qui respectent un critère.
- `SOMME.SI` additionne les montants qui respectent un critère.
- Le critère peut être un texte, un nombre ou une comparaison.

<!--
Tip : les critères contenant un opérateur s'écrivent entre guillemets, par exemple `">100"` ou `"<>Paris"`. Pour comparer à une cellule : `">"&A1`.
-->
