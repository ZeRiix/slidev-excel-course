---
layout: VisualContentLayout
kicker: Recherche de données
title: Nommer une plage
placeholder: "Capture Excel ciblée montrant une plage de catalogue sélectionnée et la zone de nom contenant `Catalogue`."
slide_info: false
image: ./image.png
---

- Nom court, clair, sans espace.
- Remplace une adresse comme `$A$2:$D$6`.
- Utile pour une table de référence.
- Plus lisible à la recopie.

```excel
=RECHERCHEV(A10;Catalogue;2;FAUX)
```

<!--
À retenir : une plage nommée est simplement un nom donné à une zone de cellules. Elle rend les formules plus lisibles et évite de répéter des références comme `$A$2:$D$6`.

Tip : pour nommer rapidement une plage, sélectionnez-la puis saisissez son nom dans la zone de nom située à gauche de la barre de formule.
-->
