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
À expliquer à l'oral :
- Une plage nommée est surtout un confort de lecture.
- Dans une formule longue, `Catalogue` est plus facile à comprendre que `$A$2:$D$6`.
- Faire le lien avec les références absolues : l'objectif est aussi d'éviter les décalages à la recopie.
- Montrer la zone de nom dans Excel avec une petite capture ou une démo directe.
-->
