# Step 1 — Générer la forêt

La première étape consiste à générer aléatoirement une forêt et à l'afficher simplement dans la console.

La forêt contient plusieurs types d'arbres, par exemple :

- des chênes
- des acacias
- des sapins

Utilisez une **Factory** pour créer les différents éléments constituant la forêt.

Plusieurs formes de forêts doivent pouvoir être générées :

- une forêt rectangulaire classique, entièrement bordée d'arbres
- une forêt magique horizontalement, dans laquelle le bord gauche communique avec le bord droit
- une forêt magique verticalement, dans laquelle le bord supérieur communique avec le bord inférieur
- une forêt entièrement magique, dans laquelle les bords opposés communiquent horizontalement et verticalement

Dans une forêt magique, un élément mobile quittant la forêt par un bord réapparaît sur le bord opposé.

Pour cette première étape, l'affichage reste volontairement simple. Chaque case est représentée par un caractère dans la console. Aucun sprite ni zoom n'est encore nécessaire.

## Points d'attention

- La génération de la forêt ne doit pas dépendre de son affichage
- Le type de forêt doit modifier la manière dont les coordonnées sont interprétées
- Le reste du programme ne doit pas multiplier les tests pour savoir si un bord est magique

---

[Retour au sujet principal](README.md)
