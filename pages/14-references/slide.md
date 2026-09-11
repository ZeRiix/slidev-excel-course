---
layout: VisualContentLayout
kicker: Références
title: Relative ou absolue ?
placeholder: Capture focus avec une formule recopiée vers le bas et une cellule de taux fixée avec $F$2. Montrer la formule dans la barre de formule et encadrer la cellule fixe.
imageSide: right
image: ./image.png
slide_info: false
---

Quand on recopie une formule, Excel adapte les références.

```excel
D5 = B5*C5
D6 = B6*C6
```

Pour garder une cellule fixe, on utilise `$`.

```excel
$F$2   // colonne F et ligne 2 bloquées
```

À retenir :

- `B5` se déplace lors de la recopie.
- `$F$2` reste fixe.
- Utile pour un taux de TVA, une remise ou un coefficient commun.
