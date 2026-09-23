---
layout: ExerciseLayout
kicker: Exercice
title: Analyse de formations en entreprise
duration: 30 min
durationLabel: durée estimée
slide_info: false
---

Créer une synthèse exploitable à partir du fichier CSV fourni.

<TheDownload label="Télécharger l'exercice" href="./exercice-tcd.zip" />

À produire :

- Un TCD qui compte les demandes par `Categorie personnel` et `Origine demande`.
- Une synthèse de la somme des `Heures` par `Domaine formation`.
- Un filtre ou segment pour explorer les résultats.
- Une modification de la source, puis une actualisation.
- Un graphique croisé dynamique lisible.

<!--
Mémo : avant de créer un TCD, vérifiez que la source est propre : en-têtes présents, colonnes cohérentes, pas de ligne vide au milieu des données.

Première analyse :

- `Categorie personnel` et `Origine demande` organisent les données ;
- `Demande` est utilisée dans `Valeurs` avec l'opération `Nombre`.

Deuxième analyse :

- `Domaine formation` organise les données ;
- `Heures` est utilisée dans `Valeurs` avec l'opération `Somme`.

Exploration :

- un filtre ou un segment doit permettre d'isoler une partie des données ;
- le choix du champ filtré doit aider à lire les résultats.

Attention : Excel peut choisir automatiquement une agrégation. Vérifiez que `Heures` utilise bien `Somme`, pas `Nombre`.

À retenir : après modification de la source, le TCD et son graphique doivent être actualisés pour refléter les nouvelles valeurs.
-->
