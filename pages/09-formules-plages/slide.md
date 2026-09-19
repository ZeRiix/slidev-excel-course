---
layout: VisualContentLayout
kicker: Formules
title: Cellules isolées et plages
placeholder: Capture très ciblée montrant une plage sélectionnée, par exemple B2:B8, puis une plage rectangulaire B2:D8. Ajouter des cadres de couleur pour distinguer cellule, plage et séparateurs.
imageSide: right
image: ./image.png
slide_info: false
---

Une formule peut cibler une cellule seule, plusieurs cellules séparées ou toute une zone.

```excel
=SOMME(B2;D2;F2)     // cellules séparées
=SOMME(B2:B8)        // plage continue
=SOMME(B2:D8)        // plage rectangulaire
=SOMME(B2:B8;D2:D8)  // plusieurs plages
```

À retenir :

- `:` signifie "de cette cellule à cette cellule".
- `;` sépare plusieurs éléments dans une fonction (plage, valeur, cellule).
- Une plage évite d'écrire toutes les cellules une par une.

<!--
À retenir : `:` désigne une plage continue. Dans Excel en français, `;` sépare généralement les arguments d'une fonction.

Attention : selon la langue ou la configuration d'Excel, `,` peut être utilisé à la place de `;`.

Tip : pendant l'écriture d'une formule, sélectionnez directement la plage à la souris plutôt que de saisir manuellement son adresse.
-->
