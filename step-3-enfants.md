# Step 3 — Ajouter les enfants

Ajoutez plusieurs enfants dans la forêt.

Pour le moment, les enfants se déplacent de manière totalement aléatoire. À chaque tour, chaque enfant choisit une direction parmi le nord, l'est, le sud et l'ouest.

Le déplacement doit respecter les contraintes suivantes :

- un enfant ne peut pas traverser un arbre
- un enfant ne peut pas traverser une tombe
- un enfant ne peut pas traverser un autre enfant
- dans une forêt magique, un enfant franchissant un bord réapparaît sur le bord opposé

Le choix du déplacement doit être confié à une **Strategy**. La stratégie initiale produit un déplacement aléatoire, mais l'architecture doit permettre d'ajouter ultérieurement d'autres comportements sans modifier la classe représentant l'enfant.

L'affichage doit permettre de sélectionner un enfant à suivre. L'enfant suivi reste alors au centre de la zone affichée pendant ses déplacements.

## Points d'attention

- L'enfant ne doit pas contenir directement l'algorithme de déplacement aléatoire
- La stratégie propose une direction, mais le moteur du jeu reste responsable de vérifier si le déplacement est possible
- La position de l'enfant appartient au modèle et non à la vue

---

[Retour au sujet principal](README.md)
