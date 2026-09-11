---
layout: ExerciseLayout
kicker: Exercice
title: Analyse de commandes
duration: 20 min
durationLabel: durée estimée
slide_info: false
---

À partir d'une liste de commandes, calculer automatiquement les statuts, les priorités et les totaux par ville.

<TheDownload label="Télécharger l'exercice" href="./exercice-commandes.zip" />

À produire :

- `Statut` : `"Réglé"` si payé, sinon `"À relancer"`.
- `Priorité` : `"Haute"` si montant `> 1000` et non payé, sinon `"Normale"`.
- Nombre de commandes à Paris avec `NB.SI`.
- Montant total des commandes à Paris avec `SOMME.SI`.

<TheFold title="Données d'exemple" :open="false">

| Ville | Client | Montant | Payé ? |
|---|---|---:|---|
| Nîmes | Martin | 665 | Oui |
| Paris | Durand | 345 | Non |
| Strasbourg | Bernard | 560 | Oui |
| Nantes | Petit | 4000 | Oui |
| Paris | Robert | 892 | Non |
| Lyon | Richard | 555 | Oui |
| Paris | Moreau | 3475 | Oui |

</TheFold>
