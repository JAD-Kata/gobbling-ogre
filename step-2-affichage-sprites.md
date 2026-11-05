# Step 2 — Afficher la forêt avec des sprites

Remplacez l'affichage brut par un affichage utilisant des sprites textuels.

Chaque case de la forêt doit être traduite en un sprite composé de plusieurs caractères. Le zoom doit être paramétrable afin de pouvoir modifier les dimensions utilisées pour représenter une case.

Toute la forêt ne doit pas nécessairement être visible à l'écran. L'affichage montre uniquement une portion de la forêt autour d'un point central.

L'affichage doit notamment gérer correctement :

- les différents types d'arbres
- les cases vides
- les limites de la portion affichée
- les forêts magiques
- le niveau de zoom

La représentation graphique d'un élément ne doit pas être stockée directement dans la forêt. La forêt contient les informations du modèle, tandis que la vue choisit le sprite correspondant.

---

[Retour au sujet principal](README.md)
