# Exercice - Catalogue produits et commandes

## Objectif

Nettoyer une liste de commandes importée, puis la compléter automatiquement à partir d'un catalogue produits.

## Données

Importer ou ouvrir les fichiers `catalogue.csv` et `commandes_importees.csv` dans Excel.

## À produire

- Nommer la plage du catalogue : `Catalogue`.
- Créer `Code produit` à partir de `Code importé` avec `REMPLACER`.
- Créer `Référence commande` avec `CONCAT(Client;" - ";Code produit)`.
- Remplir `Produit`, `Catégorie` et `Prix unitaire` avec `RECHERCHEV`.
- Éviter l'affichage brut de `#N/A` si le code n'existe pas.
- Calculer `Total` avec `Quantité * Prix unitaire` quand le prix existe.

Fonctions à chercher si besoin : `SIERREUR`, `ESTERREUR`.
