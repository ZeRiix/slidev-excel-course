---
layout: TheoryContentLayout
kicker: Recherche de données
title: INDEX + EQUIV
slide_info: false
---

`INDEX` + `EQUIV` permet de récupérer une valeur à partir d'une position trouvée automatiquement.

```excel
=INDEX(B2:B6;EQUIV(A10;A2:A6;0))
```

Lecture :

- `EQUIV(A10;A2:A6;0)` cherche le code et renvoie sa position.
- `INDEX(B2:B6;position)` récupère la valeur à cette position.
- `0` impose une correspondance exacte.

<TheHint>

`RECHERCHEV` est plus simple à lire au début. `INDEX` + `EQUIV` devient utile quand le tableau évolue ou quand la colonne à renvoyer n'est pas facile à viser avec un numéro.

</TheHint>

<!--
Mémo : `EQUIV` trouve où se trouve la donnée ; `INDEX` récupère la valeur située à cette position.

`INDEX` + `EQUIV` est plus flexible que `RECHERCHEV`, notamment lorsque la colonne à retourner se trouve à gauche ou lorsque la structure du tableau évolue.
-->
