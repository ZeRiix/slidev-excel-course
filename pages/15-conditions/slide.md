---
layout: TheoryContentLayout
kicker: Conditions
title: SI, ET, OU
slide_info: false
---

`SI` permet de choisir un résultat selon une condition.

```excel
=SI(C2>=10;"Validé";"Non validé")
```

Pour tester plusieurs conditions :

- `ET(condition1; condition2)` : toutes les conditions doivent être vraies.
- `OU(condition1; condition2)` : au moins une condition doit être vraie.

Il est possible d'imbriquer les conditions entre elles afin de construire des conditions complexes.

```excel
=SI(
  ET(D2="Non";OU(C2>1000;B2="Paris"));
  "Priorité haute";
  "Priorité normale"
)
```
